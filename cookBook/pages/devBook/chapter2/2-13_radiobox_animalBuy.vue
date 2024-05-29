<template>
  <div>
    <form>
      <fieldset>
        <legend>Today's animals</legend>
        <label>
          <input type="radio" v-model="animal" :value="animals[i]" />{{ animals[i] }}
        </label><br>
        <label>
          <input type="radio" v-model="animal" :value="animals[i+1]" />{{ animals[i+1] }}
        </label><br>
        <input class="styled-button" type="submit" value="Add to Farm" @click.prevent="addToFarm">
      </fieldset>
    </form>
    <div>
      Your farm is composed by {{ farm.join(' ') }}
    </div>

  </div>
</template>

<script>

export default {
  data () {
    return {
      animals:['🐖','🐓', '🐶'],
      animal: undefined,
      farm: [],
      i: 0
    }
  },
  computed: {

  },
  methods: {
    addToFarm () {
      if(this.animal === undefined) {return}

      this.farm.push(this.animal)

      let tempRandomFloor = Math.random()
      let tempAnimalLength = this.animals.length - 1
      this.i = Math.floor(tempRandomFloor * tempAnimalLength)

      console.log('tempRandomFloor: ', tempRandomFloor);
      console.log('tempAnimalLength: ', tempAnimalLength);
      console.log('this.i: ', this.i);

      this.animal = undefined
    }
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

#dog {
  position: absolute;
  left: 7.5em;
  top:0em;
  cursor: pointer;
}

.fade-leave-active {
  transition: opacity 2.5s;
  opacity: 0
}

</style>