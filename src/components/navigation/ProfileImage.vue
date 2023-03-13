<template>
  <img
    :src="imageLink"
    class="h-8 w-8 rounded-3xl object-contain"
    alt="User profile image"
  />
</template>

<script lang="ts" setup>
import { ref } from "vue";
const imageLink = ref(
  "https://pbs.twimg.com/profile_images/1371713662990303233/-kbnQGFp_400x400.jpg"
);
</script>
