<template>
  <p>부모로 부터 받은 값 <br> {{ this.gift }}, {{ this.decoration }}</p>
</template>

<script>
export default {
  props: ['gift', 'decoration'], // props 정의
  data(){
    return {

    }
  },
}
</script>

<style>

</style>