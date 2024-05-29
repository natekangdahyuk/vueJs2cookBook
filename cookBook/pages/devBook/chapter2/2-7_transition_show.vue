<!--
클래스 네이밍 규칙
<transition> 태그는 다양한 클래스 이름을 자동으로 생성하고 적용합니다. 예를 들어, name="fade"인 경우 다음과 같은 클래스가 사용됩니다:

fade-enter: 요소가 들어올 때 적용.
fade-enter-active: 요소가 들어오는 동안 적용.
fade-enter-to: 요소가 들어온 후 적용. (Vue 2.1.8+)
fade-leave: 요소가 나갈 때 적용.
fade-leave-active: 요소가 나가는 동안 적용.
fade-leave-to: 요소가 나간 후 적용. (Vue 2.1.8+)
*/
-->
<template>
  <div>
    <article>
      They call me fruit.<br>
      They call me fish.<br>
      They call me insect.<br>
      But actually I'm not one of those.
      <div id="solution" @click="showSolution = true">
        I am a
        <transition name="fade">
          <span id="dragon" v-show="showSolution">Dragon</span>
        </transition>
      </div>

    </article>
  </div>
</template>

<script>

export default {
  data () {
    return {
      showSolution: false
    }
  },
  computed: {

  },
  methods: {

  }
}
</script>

<style>
.styled-table {
  width: 70%;
  border-collapse: collapse;
  border-spacing: 0;
  border: 2px solid #ccc;
}

.styled-table th, .styled-table td {
  padding: 12px;
  text-align: left;
  border-bottom: 1px solid #ddd;
}

.styled-table tbody tr:nth-child(even) {
  background-color: #440404;
}

.styled-table-header {
  background-color: #007bff; /* 원하는 색상으로 변경하세요 */
  color: white; /* 헤더 텍스트 색상 */
}

/* 각 셀 사이에 구분선을 추가합니다 */
.styled-table td + td, .styled-table th + th {
  border-left: 1px solid #ddd;
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

.styled-input {
  width: 33%;
  height: 200px;
  color: white ; /* 텍스트 색상 */
  background-color: transparent; /* 배경 색상 */
  border: 1px solid #ccc; /* 테두리와 테두리 색상 */
  border-radius: 4px;/* 모서리 둥글게 */
  box-sizing: border-box; /* 패딩과 테두리를 전체 넓이에 포함 */
  padding: 5px;/* 내부 여백 */
  font-size: 16px; /* 글꼴 크기 */
}

.styled-textarea {
  color: white ; /* 텍스트 색상 */
  background-color: transparent; /* 배경 색상 */
  border: 1px solid white; /* 테두리 색상 */
  padding: 5px;
  border-radius: 4px;
}

.fade-enter-active {
  transition: opacity 4.5s;
  opacity: 1
}

.fade-enter {
  opacity: 0
}

#solution {
  cursor: pointer;
  border: 1px solid white; /* 테두리 색상 */
}


</style>