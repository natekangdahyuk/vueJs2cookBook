<template>
  <div>
    <table border="1">
      <thead>
        <tr>
          <th>Name</th>
          <th>Country</th>
          <th v-bind:class="order === 1 ? 'descending' : 'ascending'" >
            <button @click="toggleOrder">
              Eletricity
            </button>
          </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(dam, index) in damsByElecticity" :key="index">
          <td>{{ dam.name }}</td>
          <td>{{ dam.country }}</td>
          <td>{{ formatNumber(dam.electricity) }} MegaWatts</td>
        </tr>
      </tbody>
    </table>


  </div>
</template>

<script>
export default {
  data () {
    return {
      dams: [
      {name: 'Nurek Dam', country: 'Tajikistan', electricity: 3200},
      {name: 'Three Gorges Dam', country: 'China', electricity: 22500},
      {name: 'Tarbela Dam', country: 'Pakistan', electricity: 3500},
      {name: 'Guri Dam', country: 'Venezuela', electricity: 10200}
    ],
    order: 1 // means ascending
    }
  },
  computed: {
    damsByElecticity () {
      return this.dams.sort((d1, d2) => (d2.electricity - d1.electricity) * this.order)
    }

  },
  methods: {
    toggleOrder() {
      this.order *= -1;
    },
    formatNumber(value) {
      return new Intl.NumberFormat().format(value);
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

.ascending:after {
  content: "\25B2"
}

.descending:after {
  content: "\25BC"
}
</style>