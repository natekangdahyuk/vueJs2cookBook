<template>
  <div>
    <p>{{ dialogue[currentLine] }}</p>

  </div>
</template>

<script>
import { bus } from '@/pages/devBook/chapter4/4-3_eventBus.js' // 이벤트 버스 가져오기

export default {
  props: {
    iceBreaker: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      currentLine: this.iceBreaker ? 0 : -1,
      dialogue: [
        'hello',
        'how are you?',
        'fine thanks',
        'let\'s go drink!',
        'alright, where?',
        'to hello\'s bar',
        'hello?'
      ]
    }
  },
  created () {
    bus.$on('line', line => {
      // is not the line I just sent
      if (line !== this.currentLine) {
        setTimeout(() => {
          this.currentLine = (line + 1) % this.dialogue.length
          bus.$emit('line', this.currentLine)
        }, 2000)
      }
    })
  },
  mounted () {
    if (this.iceBreaker) {
      bus.$emit('line', 0)
    }
  }
}
</script>

<style>

</style>