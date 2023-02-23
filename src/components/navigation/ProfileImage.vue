<template>
  <img
    :src="imageLink"
    class="h-8 w-8 rounded-3xl object-contain"
    alt="User profile image"
  />
</template>

<script>
export default {
  name: "ProfileImage",
  data() {
    return {
      imageLink:
        "https://pbs.twimg.com/profile_images/1371713662990303233/-kbnQGFp_400x400.jpg",
    };
  },
};
</script>
