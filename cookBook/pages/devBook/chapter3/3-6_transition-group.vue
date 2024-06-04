<template>
  <div>
    <transition-group name="slide" tag="ul">
      <li v-for="topic in syllabus" :key="topic">
        <button class="styled-button" @click="completed(topic)">Done</button>{{ topic }}
      </li>
    </transition-group>

  </div>
</template>

<script>
export default {
  data () {
    return {
      syllabus: [
    	'HTML',
      'CSS',
      'Scratch',
      'JavaScript',
      'Python'
      ]
    }
  },
  computed: {
  },
  methods: {
    completed (topic) {
    	let index = this.syllabus.indexOf(topic)
    	this.syllabus.splice(index, 1)
    }
  }
}
</script>

<style>
.slide-leave-active {
  transition: all 0.5s;
  opacity: 0;
  transform: translateY(-30px);
}

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
</style>