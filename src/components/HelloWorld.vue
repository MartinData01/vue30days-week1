<script setup>
import { ref } from 'vue'
const drinkData = ref([
  {
    name: '珍珠奶茶',
    desc: '香濃奶茶搭配QQ珍珠',
    price: 50,
    stock: 20
  },
  {
    name: '冬瓜檸檬',
    desc: '清新冬瓜配上新鮮檸檬',
    price: 45,
    stock: 18
  },
  {
    name: '翡翠檸檬',
    desc: '綠茶與檸檬的完美結合',
    price: 55,
    stock: 34
  },
  {
    name: '四季春茶',
    desc: '香醇四季春茶，回甘無比',
    price: 45,
    stock: 10
  },
  {
    name: '阿薩姆奶茶',
    desc: '阿薩姆紅茶搭配香醇鮮奶',
    price: 50,
    stock: 25
  },
  {
    name: '檸檬冰茶',
    desc: '檸檬與冰茶的清新組合',
    price: 45,
    stock: 20
  },
  {
    name: '芒果綠茶',
    desc: '芒果與綠茶的獨特風味',
    price: 55,
    stock: 18
  },
  {
    name: '抹茶拿鐵',
    desc: '抹茶與鮮奶的絕配',
    price: 60,
    stock: 20
  }
])
const addItem = (num) => {
  // console.log(num)
  drinkData.value[num]['stock'] += 1
  // console.log(drinkData.value[num]['stock'])
}
const delItem = (num) => {
  // console.log(num)
  drinkData.value[num]['stock'] -= 1
  // console.log(drinkData.value[num]['stock'])
}
</script>

<template>
  <div class="main">
    <table>
      <thead>
        <tr>
          <th scope="col">品項</th>
          <th scope="col">描述</th>
          <th scope="col">價格</th>
          <th scope="col">庫存</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, key) in drinkData" :key="key">
          <td>{{ item.name }}</td>
          <td>
            <small>{{ item.desc }}</small>
          </td>
          <td>{{ item.price }}</td>
          <td>
            <button @click="delItem(key)">-</button> {{ item.stock }}
            <button v-on:click="addItem(key)">+</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style>
.main {
  margin-top: 200px;
  display: flex;
  justify-content: center;
}
table {
  padding: 50px;
  border: 1px solid #000;
  border-radius: 20px;
  & * {
    padding: 5px;
  }
}
</style>
