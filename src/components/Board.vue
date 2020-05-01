<template>
    <div class="board">
<!--        <table>-->
<!--            <tr><td><Table1 :depth="OriginalDepth"></Table1></td></tr>-->
<!--        </table>-->
        <Table :depth="OriginalDepth"></Table>
    </div>
</template>

<script>
    import Table from "@/components/Table";
    export default {
        name: "Board",
        components: {Table},
        props :{
            OriginalDepth: Number,
        },
        component :{
            Table,
        }
    }
</script>

<style scoped>
    /*.board {*/
    /*    background-color: aquamarine;*/
    /*}*/
    table {
        border: 1px solid black;
    }

</style>