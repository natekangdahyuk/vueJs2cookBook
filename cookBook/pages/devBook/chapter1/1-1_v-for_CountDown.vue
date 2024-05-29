<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">

      <v-card>
        <v-card-title class="headline">
          v-for
        </v-card-title>
        <v-card-text>
          <p>1초단위 카운트다운 하고 미사일 발사 예제</p>
        </v-card-text>
      </v-card>
      <v-card>
        <div>
          <ul>
            <li v-for="(value, index) in countdown" :key="index">키: {{ index }} :값 {{ value }}</li>
            <li> {{ countdown.length === 11 ? '' : '...'}}</li>
          </ul>
        </div>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data () {
    return {
      counter: 10,
      countdown: []
    }
  },
  mounted () {
    this.startCountdown()
  },
  methods: {
    startCountdown() {
      const intervalId = setInterval(() => {
        if (this.counter > 0) {
          this.countdown.push(this.counter--)
        } else if (this.counter === 0) {
          this.countdown.push('발사')
          clearInterval(intervalId);
        }
      }, 1000)
      console.log('Interval started with ID:', intervalId);

    } // startCountdown()
  } //methods:

}
</script>
