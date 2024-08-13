<script setup>
import { leftData } from "@/data/data";
import { rightData } from "@/data/data";

const left = leftData;
const right = rightData;
</script>

<template>
  <section class="section">
    <div class="block">
      <div v-for="item in left" @click="$emit('fromLeft', item)">{{ item.name }}</div>
    </div>

    <div class="block">
      <div v-for="item in right" @click="$emit('fromRight', item)">{{ item.name }}</div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.section {
  margin-top: 50px;
  display: flex;
  justify-content: space-between;
}

.block {
  width: 48%;
  line-height: 40px;
  display: grid;
  gap: 15px;
  grid-template-columns: repeat(4, 1fr);
  background-color: black;
  border-radius: 15px;
  padding: 20px;
  text-align: center;

  div {
    background-color: greenyellow;
    border-radius: 15px;
    cursor: pointer;
    transition: 0.4s;

    &:hover {
      scale: 1.1;
    }
  }
}
</style>
