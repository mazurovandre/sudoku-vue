<template>
    <td class="cell" 
    @click="handleClick">
    {{ convertedValue(value) }}

        <!-- <input type="number" maxlength="1" /> -->

    </td>
</template>

<script>
    export default {
        name: 'GameCell',
        props: {
            cellIndex: Object,
            value: String
        },
        setup(props, {emit}) {
            const handleClick = () => {
                emit('selectCell', props.cellIndex)
            }

            const convertedValue = str => str.replace('.', '')
            return {
                handleClick,
                convertedValue
            }
        }
    }
</script>

<style lang="scss" scoped>
.cell {
    width: 50px;
    height: 50px;
    border: none;
    outline: none;
    border: 1px solid gray;
    cursor: pointer;
}
input {
    width: 100%;
    height: 100%;
    padding: 0;
    border: none;
    cursor: pointer;
}
</style>