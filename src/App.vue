<script setup>
import { ref } from "vue";

// Define order items with initial counts
const items = ref([
  { name: "Eggs", count: 0 },
  { name: "Tortillas", count: 0 },
  { name: "Chocolate", count: 0 }
]);

const increaser=(item)=> {
  item.count++;
}

const decreaser=(item)=> {
  if(item.count>0){
    item.count--;
  }
};
  
</script>

<template>
  <div class="container">
    <!--Logo-->
    <div>
      <a href="https://vite.dev" target="_blank">
        <img src="/vite.svg" class="logo" alt="Vite logo" />
      </a>
      <a href="https://vuejs.org/" target="_blank">
        <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
      </a>
    </div>

    <h1>Order Items</h1>
    <div v-for="item in items" :key="item.name" class="order-item">
      <span>{{ item.name }}</span>
      <button @click="decreaser(item)">-</button>
      <span> : {{ item.count }} </span>
      <button @click="increaser(item)">+</button>
    </div>
  </div>
</template>


 