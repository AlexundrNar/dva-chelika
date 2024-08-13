<script setup>
import { computed ,ref } from 'vue' 
import ItemsSelected from './components/ItemsSelected.vue'
import ItemsInventory from './components/ItemsInventory.vue'

const leftData = ref([])
const rightData = ref({})

const addToLeft = (item) => {
  leftData.value.length < 6 ? leftData.value.push(item) : null
}

const deleteFromLeft = (id) => {
  leftData.value = leftData.value.filter(item => item.id !== id)
}

const addToRight = (item) => {
  rightData.value = item
}


</script>

<template>
  <main class="main">
    <ItemsSelected :leftArray="leftData" :rightObj="rightData" @deleteFromLeft="deleteFromLeft"/>
    <ItemsInventory @fromLeft="addToLeft" @fromRight="addToRight"/>
  </main>
</template>

<style scoped lang="scss">
.main {
  width: 100vw;
  max-width: 1440px;
  padding: 0 20px;
  margin: 0 auto;
  padding-top: 60px;
}
</style>
