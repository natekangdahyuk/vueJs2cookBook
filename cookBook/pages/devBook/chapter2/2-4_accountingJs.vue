<template>
  <div>
    <!-- 상관없지만 가독성을 위해 테이블 스타일을 추가해 보았다. -->

    <div>
      <table class="styled-table">
        <thead>
          <tr>
            <th class="styled-table-header">Item</th>
            <th class="styled-table-header">Price</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(item, index) in inventory" :key="index">
            <td>{{ item.name }}</td>
            <td class="price">{{ item.price | dollars }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import accounting from '../../../lib/accounting.0.3.2.js'

Vue.filter('dollars', function (money) {
  return accounting.formatMoney(money)  // basic : dollars, 소수점 2자리
})

export default {
  data () {
    return {
      inventory: [
        {name: 'tape measure', price: '7'},
        {name: 'stamp', price: '0.01'},
        {name: 'shark tooth', price: '1.5'},
        {name: 'iphone', price: '999'}
      ],


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

.price {
  text-align: right
}
</style>