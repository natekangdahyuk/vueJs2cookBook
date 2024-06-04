<template>
  <div class="container">
    <button class="styled-button" @click="showRecipe= !showRecipe">Recipe</button>
    <button class="styled-button" @click="showNews= !showNews">Breaking News</button>
    <Puff>
      <article v-if="showRecipe" class="card">
        <h3>
          Apple Pie Recipe
        </h3>
        <p>
          Ingredients: apple pie. Procedure: serve hot.
        </p>
      </article>
    </Puff>
    <Puff>
      <article v-if="showNews" class="card">
        <h3>
          Breaking news
        </h3>
        <p>
          Donald Duck is the new president of the USA.
        </p>
      </article>
    </Puff>

  </div>
</template>

<script>
export default {
  data () {
    return {
      showRecipe: false,
      showNews: false
    }
  }
}
</script>

<style>


.container {
  text-align: center;
  width: 400px; /* 고정 너비 */
  margin: 0 auto;
  padding: 1em;
  border-radius: 8px; /* 모서리 둥글게 */
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5); /* 그림자 효과 */
}

.card {
  position: relative;
  background-color: FloralWhite;
  width: 100%; /* 카드가 container의 너비를 채우도록 설정 */
  max-width: 400px; /* 카드의 최대 너비 */
  height: auto;
  margin: 1em 0; /* 카드 요소의 상하 마진 */
  padding: 1em;
  border-radius: 8px;
  box-shadow: 0px 0px 10px 2px rgba(0, 0, 0, 0.3);
  overflow: hidden;
  transition: width 0.5s ease-out;
}

.card h3 {
  margin-top: 0;
  font-size: 1.5em;
  color: #333;
}

.card p {
  font-size: 1em;
  line-height: 1.5;
  color: #555;
}


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