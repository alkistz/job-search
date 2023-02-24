<template>
  <li class="mb-7">
    <router-link
      to="/jobs/results/1"
      class="mx-auto block rounded border-solid border-brand-gray-2 bg-white hover:shadow-gray"
    >
      <div class="mx-8 border-b border-solid border-brand-gray-2 pt-5 pb-2">
        <h2 class="mb-2 text-2xl">BBQ Administrator</h2>

        <div class="flex flex-row align-middle">
          <div class="mr-5">
            <span>Alkis</span>
          </div>

          <div>
            <span>Kordelio</span>
          </div>
        </div>
      </div>
      <div class="px-8 py-4">
        <div>
          <h3 class="mt-1 mb-2">Qualifications</h3>
          <ul class="list-disc pl-8">
            <li>Good with the grill</li>
            <li>5 years of meat handling experience</li>
            <li>Experience with butcher price negotiations</li>
            <li>At least a small beer belly</li>
          </ul>
        </div>
        <div class="mt-2 text-center">
          <router-link to="/jobs/results/1" class="text-brand-blue-1"
            >Expand</router-link
          >
        </div>
      </div>
    </router-link>
  </li>
</template>

<script>
export default {
  name: "JobListing",
};
</script>
