<template>
  <div class="abs-tr text-base flex items-center pt-3 pr-3">
    <a v-if="githubUrl"
       :href="githubUrl"
       target="_blank"
       alt="GitHub"
       class="icon"
    >
      <carbon-logo-github/>
    </a>
    <a v-if="gitlabUrl"
       :href="gitlabUrl"
       target="_blank"
       alt="GitLab"
       class="icon"
    >
      <cib-gitlab/>
    </a>
    <a v-if="twitterHandle"
       :href="`https://twitter.com/${twitterHandle}`"
       target="_blank"
       alt="Twitter"
       class="icon"
    >
      <carbon-logo-twitter/>
      {{ twitterHandle }}
    </a>
    <a v-if="mastodonHandle"
       :href="createMastodonUrl(mastodonHandle)"
       target="_blank"
       alt="Mastodon"
       class="icon"
    >
      <cib-mastodon/>
      {{ mastodonHandle }}
    </a>
  </div>
</template>

<script lang="ts">
export default {
  props: {
    twitterHandle: String,
    mastodonHandle: String,
    githubUrl: String,
    gitlabUrl: String,
  },
  methods: {
    createMastodonUrl(handle: string) {
      const [, name, fediServer] = handle.split('@');
      return `https://${fediServer}/@${name}`
    }
  }
};
</script>

<style>
  .icon {
    @apply icon-btn !p-1 !border-none !hover:text-white;
  }
</style>
