<script>
export default {
  props: {
    main: String,
    sub: String,
  },
};
</script>

<template>
  <div class="slidev-layout banner has-logo">
    <h1>
      <span class="words">
        <p class="words-line revert">{{main}}</p>
        <p class="words-line" v-if="sub">
          <span class="animated-header-text">{{sub}}</span>
        </p>
      </span>
    </h1>
  </div>
</template>