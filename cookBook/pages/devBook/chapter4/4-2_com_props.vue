<!--
  props는 단방향 통신이다.
  고정된 값이거나 동적으로 변경될 수 있다.

-->
<template>
  <div>
    <label>Sound level</label>
    <input class="styled-input" type="number" v-model.number="soundLevel">
    <sound-icon-4-2 :level="soundLevel"></sound-icon-4-2>

  </div>
</template>

<script>
export default {
  data () {
    return {
      soundLevel: 0
    }
  }

}
</script>

<style>
.styled-input {
  width: 33%;

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

.styled-select {
  color: white; /* 텍스트 색상 */
  background-color: #424242; /* 배경 색상 */
  border: 1px solid white; /* 테두리 색상 */
  padding: 5px;
  /* 화살표를 보이도록 설정 */
  -webkit-appearance: menulist;
  -moz-appearance: menulist;
  appearance: menulist;
}

/* div 안에 간단한 텍스트 표시 */
.styled-simple {
  margin-top: 10px; /* 위 여백 추가 */
  color: white; /* 텍스트 색상 */
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