<template>
    <div class="difficulty">
        <button @click="handleClick('easy')">Easy</button>
        <button @click="handleClick('medium')">Medium</button>
        <button @click="handleClick('hard')">Hard</button>
    </div>
</template>

<script>
    export default {
        name: 'DifficultySelector',
        setup(_, {emit}) {
            const handleClick = difficulty => {
                emit('selectDifficulty', difficulty)
            }
            return {
                handleClick
            }
        }
    }
</script>

<style lang="scss" scoped>
.difficulty {
    display: flex;
}
</style>