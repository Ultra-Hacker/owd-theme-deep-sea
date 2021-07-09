<template>
  <div class="owd-desktop__system-bar__content">
    <slot />
  </div>
</template>

<script setup>
import {defineProps} from "vue";

const props = defineProps({
  config: Object
})
</script>

<style scoped lang="scss">
.owd-desktop__system-bar__content {
  position: absolute;
  background: $owd-desktop-system-bar-menu-content-background;
  box-shadow: 0 0 0 1px $owd-desktop-system-bar-menu-content-border-color;
  color: $owd-desktop-system-bar-menu-content-color;
  border-radius: 5px;
  z-index: 999;
}
</style>

<style lang="scss">
.owd-desktop {
  &__system-bar {
    &--position-top {
      .owd-desktop__system-bar__content {
        top: 48px;
      }
    }

    &--position-bottom {
      .owd-desktop__system-bar__content {
        bottom: 48px;
      }
    }
  }
}
</style>