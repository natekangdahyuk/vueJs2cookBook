<!-- 6개의 행성을 data() worlds 변수에 배열로 선언 -->
<!-- v-for 로 ul 에서 보여줘라.-->
<!-- 행성 옆에 삭제 버튼을 만들어라.-->
<!-- 행성 추가를 만들어라.-->
<template>
  <div>
    <ul>
      <li v-for="(world,i) in worlds" :key="i">
        {{ i }}. {{ world }}
        <button class="styled-button" @click="worlds.splice(i, 1)">삭제</button>
      </li>
    </ul>
    <input class="styled-input" v-model="newWorld" />
    <button class="styled-button" @click="worlds.push(newWorld)">추가</button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      worlds: ['행성1', '행성2', '행성3', '행성4', '행성5', '행성6'],
      newWorld: ''
    }
  },
}
</script>

<style>
.styled-input {
  color: white ; /* 텍스트 색상 */
  background-color: transparent; /* 배경 색상 */
  border: 1px solid white; /* 테두리 색상 */
  padding: 5px;
  border-radius: 4px;
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

</style>