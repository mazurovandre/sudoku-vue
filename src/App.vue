<template>
  <div class="container">
    <div class="game">
      <DifficultySelector @selectDifficulty='generatePuzzle' />
      <GameField v-if="puzzleInitialString" :puzzleString='puzzleInitialString'/>
    </div>
  </div>
  
</template>

<script>
import { ref } from '@vue/reactivity'
import DifficultySelector from './components/DifficultySelector.vue'
import GameField from './components/GameField.vue'
import sudokuScript from './scripts/sudoku.js'

export default {
  name: 'App',
  components: {
    GameField,
    DifficultySelector
  },
  setup() {
    const columnIndex = null;
    const rowIndex = null;
    let puzzleInitialString = ref('');
    let puzzleResultString = ref('');

    const generatePuzzle = difficulty => {
      puzzleInitialString.value = sudokuScript.sudoku.generate(difficulty);
      puzzleResultString.value = sudokuScript.sudoku.solve(puzzleInitialString.value);
    }
    return {
      columnIndex,
      rowIndex,
      generatePuzzle,
      puzzleInitialString,
      puzzleResultString
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  margin: 0 auto;
  text-align: center;
}

.game {
  display: inline-block;
  margin: 0 auto;
}
</style>
