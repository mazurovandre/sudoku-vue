<template>
  <div class="container">
    <table>
      <tbody>
        <tr v-for="(i, indexRow) in puzzleArray.length" 
          :key="'row-' + indexRow"
          >
          <GameCell v-for="(j, indexColumn) in puzzleArray[indexRow]" 
          :key="'column-' + indexRow + indexColumn"
          :value="puzzleString[indexRow * 9 + indexColumn]"
          />
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity';
import GameCell from './GameCell.vue';
export default {
  name: 'GameField',
  components: {
    GameCell
  },
  props: {
    puzzleString: String
  },
  setup(props) {
    const puzzleArray = ref([]);

    for (let i = 0; i < 9; i++) {
      puzzleArray.value[i] = props.puzzleString.slice(9 * i, 9 + (9 * i))
    }

    const calcIndex = index => {
      const columnIndex = index % 3 === 0 ? 3 : index % 3;
      const rowIndex = Math.ceil(index / 3);

      return {
        columnIndex, rowIndex, puzzleArray
      }
    }

    return {
      calcIndex,
      puzzleArray
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  // display: grid;
  // grid-template-columns: repeat(3, 150px);
  // grid-template-rows: repeat(3, 150px);
  margin: 0 auto;
  border-bottom: 2px solid black;
  border-right: 2px solid black;
}
table {
  border-collapse: collapse;
}
</style>
