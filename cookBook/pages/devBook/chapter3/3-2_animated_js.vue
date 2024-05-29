<!--설치:
  npm install velocity-animate
  npm install --save-dev @types/velocity-animate
-->
<template>
  <div>
    <button class="styled-button" @click="toggleTaxi">
      {{ taxiCalled ? '보내기' : '부르기.' }}
    </button>
    <transition
      @enter="enter"
      @leave="leave"
      :css="false"
    >
      <p v-if="taxiCalled">😎</p>
    </transition>
  </div>
</template>

<script>
import Velocity from 'velocity-animate';

export default {
  data () {
    return {
      taxiCalled: false
    }
  },
  computed: {

  },
  methods: {
    toggleTaxi() {
      this.taxiCalled = !this.taxiCalled
    },
    enter (el) {
      Velocity(el,
        {opacity: [1, 0], translateX: ["0px", "600px"]},
        {duration: 2000, easing: "ease-out"})
    },
    leave(el, done) {
      Velocity(el,
      {opacity: [0, 1], translateX: ["600px", "0px"]},
      {duration: 2000, easing: "ease-out", complete: done}
      )
    }

  }
}
</script>

<style>

.styled-button {
  background-color: #4CAF50; /* 녹색 배경 */
  border: none; /* 테두리 없음 */
  color: white; /* 흰색 텍스트 */
  padding: 15px 32px; /* 패딩 */
  text-align: center; /* 텍스트 가운데 정렬 */
  text-decoration: none; /* 텍스트 장식 없음 */
  display: inline-block; /* 인라인 블록 요소 */
  font-size: 16px; /* 글꼴 크기 */
  margin: 4px 2px; /* 마진 */
  cursor: pointer; /* 커서 포인터 */
  border-radius: 12px; /* 모서리 둥글게 */
  transition: background-color 0.3s, transform 0.3s; /* 배경색과 변형의 트랜지션 효과 */
}

.styled-button:hover {
  background-color: #45a049; /* 호버 시 배경색 변경 */
  transform: scale(1.05); /* 호버 시 약간 커짐 */
}

.styled-button:active {
  background-color: #3e8e41; /* 클릭 시 배경색 변경 */
  transform: scale(1); /* 클릭 시 원래 크기로 */
}

.styled-button:focus {
  outline: none; /* 포커스 시 아웃라인 제거 */
  box-shadow: 0 0 0 2px rgba(76, 175, 80, 0.5); /* 포커스 시 그림자 효과 */
}


.texi_call {
  transition: all 0.5s ease-out;
}

.texi_out {
  transition: all 0.5s ease-in;
}
</style>