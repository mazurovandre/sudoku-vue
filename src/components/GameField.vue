<template>
  <div class="container">
    <CellGroup v-for="i in 9" :key="i"/>
  </div>
</template>

<script>
// import
import CellGroup from './CellGroup.vue'
export default {
  name: 'GameField',
  components: {
    CellGroup
  }
}
</script>

<style lang="scss" scoped>
.container {
  display: grid;
  grid-template-columns: repeat(3, 150px);
  grid-template-rows: repeat(3, 150px);
  margin: 0 auto;
  border-bottom: 2px solid black;
  border-right: 2px solid black;
}
</style>
