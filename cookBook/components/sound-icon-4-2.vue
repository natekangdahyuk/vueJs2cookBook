<template>
  <span>{{ soundEmojis[level] }}</span>
</template>

<script>
export default {
  props: {
    level: Number
  },
  data () {
    return {
      soundEmojis: ['🔇', '🔈', '🔉', '🔊']
    }
  }
}
</script>

<style>

</style>