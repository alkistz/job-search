<template>
  <header :class="['w-full', 'text-sm', headerHeightClass]">
    <div class="fixed top-0 left-0 h-16 w-full bg-white">
      <div
        class="mx-auto flex h-full flex-nowrap border-b border-solid border-brand-gray-1 px-8"
      >
        <router-link
          :to="{ name: 'Home' }"
          class="flex h-full items-center text-xl"
          >Alkis careers</router-link
        >
        <nav class="ml-12 h-full">
          <ul class="flex h-full list-none">
            <li
              v-for="menuItem in menuItems"
              :key="menuItem.text"
              class="ml-9 h-full first:ml-0"
            >
              <router-link
                :to="menuItem.url"
                class="flex h-full items-center py-2.5"
                >{{ menuItem.text }}</router-link
              >
            </li>
          </ul>
        </nav>
        <div class="ml-auto flex h-full items-center">
          <ProfileImage v-if="isLoggedIn" />
          <ActionButton v-else text="Sign in" @click="loginUser" />
        </div>
      </div>
      <TheSubnav v-if="isLoggedIn" />
    </div>
  </header>
</template>

<script lang="ts" setup>
import { useUserStore } from "@/stores/user";
import { ref, computed } from "vue";

import ActionButton from "@/components/shared/ActionButton.vue";
import ProfileImage from "@/components/navigation/ProfileImage.vue";
import TheSubnav from "@/components/navigation/TheSubnav.vue";

const userStore = useUserStore();
const loginUser = userStore.loginUser;
const isLoggedIn = computed(() => userStore.isLoggedIn);

const headerHeightClass = computed(() => ({
  "h-16": !isLoggedIn.value,
  "h-32": isLoggedIn.value,
}));

const menuItems = ref([
  { text: "Teams", url: "/teams" },
  { text: "Locations", url: "/" },
  { text: "Life at Alkis Corp", url: "/" },
  { text: "Students", url: "/" },
  { text: "Jobs", url: "/jobs/results" },
]);
</script>
