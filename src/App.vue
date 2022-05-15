<template>
  <div class="container">
    <div class="game">
      <GameField />
    </div>
  </div>
  
</template>

<script>
import GameField from './components/GameField.vue'

export default {
  name: 'App',
  components: {
    GameField
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
