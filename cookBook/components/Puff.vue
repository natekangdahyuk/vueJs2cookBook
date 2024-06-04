<template>
  <transition :enter-active-class="enterActiveClass" :leave-active-class="leaveActiveClass">
    <slot></slot>
  </transition>
</template>

<script>
export default {
  props: {
    enterActiveClass: {
      type: String,
      default: 'magictime puffIn'
    },
    leaveActiveClass: {
      type: String,
      default: 'magictime puffOut'
    }
  }
}
</script>