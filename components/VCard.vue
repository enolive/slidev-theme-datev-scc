<template>
  <div class="abs-tr text-base flex items-center pt-3 pr-3">
    <a
      v-if="githubUrl"
      :href="githubUrl"
      target="_blank"
      alt="GitHub"
      class="icon-btn !p-1 !border-none !hover:text-white"
    >
      <carbon-logo-github />
    </a>
    <a
      v-if="twitterHandle"
      :href="`https://twitter.com/${twitterHandle}`"
      target="_blank"
      alt="Twitter"
      class="icon-btn !p-1 !border-none !hover:text-white"
    >
      <carbon-logo-twitter /> {{ twitterHandle }}
    </a>
  </div>
</template>

<script lang="ts">
export default {
  props: {
    twitterHandle: String,
    githubUrl: String,
  },
};
</script>