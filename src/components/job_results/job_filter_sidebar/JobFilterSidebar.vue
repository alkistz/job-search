<template>
  <div
    class="flex w-96 flex-col border-r border-solid border-brand-gray-1 bg-white p-4"
  >
    <section class="pb-5">
      <div class="flex flex-row justify-between">
        <h3 class="my-4 text-base font-semibold">What do you want to do?</h3>
        <div class="flex items-center text-sm">
          <ActionButton text="Clear Filters" type="secondary" />
        </div>
      </div>
      <JobFiltersSidebarCheckboxGroup
        header="Degrees"
        :unique-values="UNIQUE_DEGREES"
        :action="userStore.ADD_SELECTED_DEGREES"
      />

      <JobFiltersSidebarCheckboxGroup
        header="Job Types"
        :unique-values="UNIQUE_JOB_TYPES"
        :action="userStore.ADD_SELECTED_JOB_TYPES"
      />

      <JobFiltersSidebarCheckboxGroup
        header="Organizations"
        :unique-values="UNIQUE_ORGANIZATIONS"
        :action="userStore.ADD_SELECTED_ORGANIZATIONS"
      />
    </section>
  </div>
</template>

<script lang="ts" setup>
import { computed } from "vue";

import ActionButton from "@/components/shared/ActionButton.vue";
import JobFiltersSidebarCheckboxGroup from "@/components/job_results/job_filter_sidebar/JobFiltersSidebarCheckboxGroup.vue";

import { useDegreesStore } from "@/stores/degrees";
import { useJobsStore } from "@/stores/jobs";
import {  useUserStore } from "@/stores/user";

const degreesStore = useDegreesStore();
const jobsStore = useJobsStore();
const userStore = useUserStore();

const UNIQUE_DEGREES = computed(() => degreesStore.UNIQUE_DEGREES);
const UNIQUE_ORGANIZATIONS = computed(() => jobsStore.UNIQUE_ORGANIZATIONS);
const UNIQUE_JOB_TYPES = computed(() => jobsStore.UNIQUE_JOB_TYPES);
</script>
