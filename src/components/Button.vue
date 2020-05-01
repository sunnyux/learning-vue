<template>
    <button :class="type"><slot/></Button>
</template>

<script>
    export default {
        name: "Button",
        props: ["type"]
    }
</script>

<style scoped>
button.primary {
    background-color: deepskyblue;
    color: aliceblue;
}
</style>