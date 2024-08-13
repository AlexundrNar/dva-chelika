<script setup>
defineProps({
  leftArray: Array,
  rightObj: {}
})
</script>

<template>
  <section class="section">
    <div class="block left">
      <div v-for="item in leftArray" @click="$emit('deleteFromLeft', item.id)">{{ item.name }}</div>
      <p>selected: {{ leftArray.length }} / 6</p>
    </div>

    <div class="block right">
      <div>
        <p>{{ rightObj.id }}</p>
        <p>{{ rightObj.name }}</p>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.section {
  display: flex;
  justify-content: space-between;
}

.block {
  position: relative;
  width: 300px;
  height: 170px;
  
  background-color: black;
  border-radius: 15px;

  div {
    line-height: 48px;
    text-align: center;
    background-color: greenyellow;
    border-radius: 15px;
    cursor: pointer;
  }
}

.left {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  padding: 20px 20px 50px;
  gap: 12px;

  div {
    height: max-content;
    &:hover {
      scale: 1.08;
    }
  }

  p {
    position: absolute;
    bottom: 10px;
    left: 0;
    right: 0;
    color: white;
    text-align: center;
  }
}

.right {
  padding: 20px;

  div {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
}
</style>
