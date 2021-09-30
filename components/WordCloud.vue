<template>
  <div>
    <ul aria-label="Word Cloud">
      <li
        v-for="(item, index) in list"
        :style="{
          'font-size': `calc(${randomSize()} * 0.5rem)`,
          color: randomColor(),
        }"
      :key="index">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
export default {
  name: "WordCloud",
  props: {
    list: Array,
  },
  methods: {
    randomColor() {
      const colors = [
        "#3b8d21",
        "#4158af",
        "#97d986",
        "#84d3cc",
        "#e199e7",
        "#a41b4d",
        "#d3983e",
        "#8f0bd2",
      ];
      return colors[Math.floor(Math.random() * colors.length)];
    },

    randomSize() {
      const min = 2;
      const max = 9;
      return Math.floor(Math.random() * (max - min + 1) + min);
    },
  },
};
</script>

<style lang="postcss" scoped>
ul {
  list-style: none;
  padding-left: 0;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  width: 85%;

  li {
    display: inline;
    padding: 0.125rem 0.5rem;
    margin: 0;
    position: relative;
    line-height: 3.5rem;
  }
}
</style>
