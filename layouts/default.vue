<script>
import {props} from '../util/props'

export default {
  props: {
    ...props
  }
}
</script>

<template>
  <div class="slidev-layout default"
       :class="!disableLogo ? 'has-logo' : ''"
  >
    <div class="my-auto w-full">
      <slot />
    </div>
  </div>
</template>

