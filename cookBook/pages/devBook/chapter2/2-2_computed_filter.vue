<template>
  <div>
    <h3>List of expensive experiments</h3>
    <ul>
      <li v-for="(experiment, index) in experiments" :key="index">{{ experiment.name }}, {{ experiment.cost }}, {{ experiment.field }}</li>
    </ul>

    <br>
    <h3>List of non Physics</h3>
    <ul>
      <li v-for="(exp, index) in computedNonPhysics" :key="index">{{ exp.name }}, {{ exp.cost }}, {{ exp.field }}</li>
    </ul>

    <br>
    <h3>Search term</h3>
    <input class="styled-input" v-model="term">
    <ul>
      <li v-for="(exp, index) in allExceptTerm" :key="index">{{ exp.name }}, {{ exp.cost }}, {{ exp.field }}</li>
    </ul>

    <br>
    <h3>Search nonPhysics and less 3 uro</h3>
    <ul>
      <li v-for="(exp, index) in nonPhysics(lowCost(experiments))" :key="index">{{ exp.name }}, {{ exp.cost }}, {{ exp.field }}</li>
    </ul>

  </div>
</template>

<script>
export default {
  data () {
    return {
      experiments: [
    	{name: 'RHIC Ion Collider', cost: 650, field: 'Physics'},
      {name: 'Neptune Undersea Observatory', cost: 100, field: 'Biology'},
      {name: 'Violinist in the Metro', cost: 3, field: 'Psychology'},
      {name: 'Large Hadron Collider', cost: 7700, field: 'Physics'},
      {name: 'DIY Particle Detector', cost: 0, field: 'Physics'}
    ],
    term: ''
    }
  },
  computed: {
    computedNonPhysics () {
      return this.experiments.filter(exp => exp.field !== 'Physics')
    },

    allExceptTerm () {
      return this.experiments
        .filter(exp => exp.field.indexOf(this.term) === -1)
    },
  },
  methods: {
    nonPhysics (list) {
      return list.filter(exp => exp.field !== 'Physics')
    },
    lowCost (list) {
      return list.filter(exp => exp.cost <= 3)
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

.styled-input {
  color: white ; /* 텍스트 색상 */
  background-color: transparent; /* 배경 색상 */
  border: 1px solid white; /* 테두리 색상 */
  padding: 5px;
  border-radius: 4px;
}
</style>