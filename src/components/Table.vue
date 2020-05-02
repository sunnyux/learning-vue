<template>
    <table>
        <tr>
            <td v-if="depth>0"><Table :depth="depth-1"></Table></td>
            <td v-else>;)</td>
        </tr>
    </table>
</template>

<script>
    export default {
        name: "Table",
        props: {
            depth: Number,
        },
    }
</script>

<style scoped>
    table {
        border: 1px solid black;
        width: 10vw;
        height: 10vw
    }
</style>