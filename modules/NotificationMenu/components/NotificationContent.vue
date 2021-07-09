<template>
  <div>
    <DesktopSystemBarMenuContent
        v-if="opened"
        class="owd-desktop__notification__container"
        v-click-outside="menuClose"
    >

      <NotificationList class="col col-notification-list" />

    </DesktopSystemBarMenuContent>

    <NotificationListFloating v-show="!opened" />
  </div>
</template>

<script setup>
import { defineProps, defineEmit } from 'vue'
import DesktopSystemBarMenuContent from '../../../components/SystemBar/components/SystemBarMenuContent.vue'
import NotificationList from "./NotificationList/NotificationList.vue";
import NotificationListFloating from "./NotificationListFloating/NotificationListFloating.vue";

const props = defineProps({
  opened: Boolean
})

const emit = defineEmit([
  'close'
])

function menuClose() {
  emit('close')
}
</script>

<style scoped lang="scss">
.owd-desktop__notification__container {
  display: grid;
  width: 500px;
  max-width: calc(100% - 32px);
  height: 500px;
  max-height: 60vh;
  line-height: 32px;
  padding: 16px 0;
  left: 50%;
  transform: translateX(-50%);

  .col-notification-list {
    padding: 8px 24px;

    @media(max-width: 600px), (max-height: 400px) {
      padding: 4px 16px;
    }
  }
}
</style>