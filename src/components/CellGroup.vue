<template>
    <div class="group">
        <GameCell v-for="i in 9" :key="i"/>
    </div>
</template>

<script>
import GameCell from './GameCell.vue'
    export default {
        name: 'CellGroup',
        components: {
            GameCell
        }
    }
</script>

<style lang="scss" scoped>
.group {
  display: grid;
  grid-template-columns: repeat(3, 50px);
  grid-template-rows: repeat(3, 50px);
  margin: 0 auto;
//   border: 2px solid black;
  border-top: 2px solid black;
  border-left: 2px solid black;
}
</style>