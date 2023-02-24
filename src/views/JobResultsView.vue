<template>
  <div class="flex w-full flex-row flex-nowrap">
    <JobFilterSidebar />
    <JobListings />
  </div>
</template>

<script>
import JobFilterSidebar from "@/components/job_results/job_filter_sidebar/JobFilterSidebar.vue";
import JobListings from "@/components/job_results/JobListings.vue";

export default {
  name: "JobResultsView",
  components: {
    JobFilterSidebar,
    JobListings,
  },
};
</script>
