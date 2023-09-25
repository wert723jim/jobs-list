<template>
  <div class="app">
    <header>
      <div class="title">
        <h1>Jobs List</h1>
      </div>
      <div class="order">
        <button @click="handleClick('title')">order by title</button>
        <button @click="handleClick('salary')">order by salary</button>
        <button @click="handleClick('location')">order by location</button>
      </div>
    </header>
    <JobList :jobs="jobs" :order="order"/>
  </div>
</template>

<script setup lang="ts">
import JobList from './components/JobsList.vue'
import { ref } from 'vue'
import Job from './types/Job'
import OrderTerm from './types/OrderTerm'

const jobs = ref<Job[]>([ 
  { title: 'farm worker', location: 'lon lon ranch', salary: 30000, id: '1'},
  { title: 'cuarryman', location: 'geath mountain', salary: 20000, id: '2'},
  { title: 'zuarryman', location: 'death mountain', salary: 1000, id: '3'},
  { title: 'duarryman', location: 'jeath mountain', salary: 100000, id: '4'},
  { title: 'euarryman', location: 'leath mountain', salary: 50000, id: '5'},
])
// generic argument
const order = ref<OrderTerm>('title')

const handleClick = (term: OrderTerm) => {
  order.value = term
}

</script>

<style scoped>
header {
  text-align: center;
}
header .order {
  margin-top: 20px;
}
button {
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 3px;
  cursor: pointer;
  font-weight: bold;
}
</style>
