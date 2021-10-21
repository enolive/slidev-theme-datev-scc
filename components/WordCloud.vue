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
import {PropType} from 'vue'

export default {
  name: 'WordCloud',
  props: {
    list: Array as PropType<Array<string>>,
  },
  methods: {
    randomColor() {
      const colors = [
        'hsl(96, 65%, 30%)',
        'hsl(96, 65%, 40%)',
        'hsl(84, 63%, 50%)',
        'hsl(84, 63%, 70%)',
        'hsl(180, 96%, 20%)',
        'hsl(180, 96%, 30%)',
        'hsl(180, 96%, 40%)',
        'hsl(180, 96%, 50%)',
      ]
      return colors[Math.floor(Math.random() * colors.length)]
    },
    randomSize() {
      const min = 2
      const max = 9
      return Math.floor(Math.random() * (max - min + 1) + min)
    },
  },
}
</script>

<style lang="postcss" scoped>
ul {
  @apply list-none px-0 flex flex-wrap items-center justify-center;
  li {
    @apply leading-15 px-2 relative m-0 inline;
  }
}
</style>
