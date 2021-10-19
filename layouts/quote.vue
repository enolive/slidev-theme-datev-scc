<!--
  Taken from the wonderful vuetiful theme

  https://github.com/LinusBorg/slidev-theme-vuetiful/blob/main/layouts/quote.vue
-->
<script>
export default {
  props: {
    author: String,
    link: String,
  },
};
</script>

<template>
  <div class="slidev-layout quote has-logo">
    <div class="flex flex-col justify-center h-full z-2 max-w-[750px] pl-5">
      <div data-quote-container class="mb-4 text-5xl relative">
        <slot />
      </div>
      <hr class="w-48 border-t-5 border-vgreen mb-2" />
      <p v-if="author" class="italic text-xl font-extralight">
        <a v-if="link" :href="link">{{ author }}</a>
        <template v-else>{{ author }}</template>
      </p>
    </div>
  </div>
</template>

<style lang="postcss" scoped>
[data-quote-container]::before {
  content: "\„";
  @apply text-8xl absolute -bottom-1 -left-12 font-serif;
}
</style>