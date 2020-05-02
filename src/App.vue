<template>
  <div>
    <tree v-show="false" :tree-data="tree"></tree>

    <h2>Table:</h2>
    <Board :original-depth="depth"></Board>

    <div></div>
    <Slider v-model="depth"></Slider>
    <span>Nesting depth: {{depth}}</span>

  </div>

</template>

<script>
  import Tree from "@/components/Tree";
  import Board from "@/components/Board";
  import Slider from "@/components/Slider";

  export default {
    data()  {
      return {
        depth: 50,
        tree: {
          label: "A cool folder",
          children: [
            {
              label: "A cool sub-folder 1",
              children: [
                { label: "A cool sub-sub-folder 1" },
                { label: "A cool sub-sub-folder 2" }
              ]
            },
            { label: "This one is not that cool" }
          ]
        }
      }
    },
    components: {
      Tree,
      Board,
      Slider,
    }
  };
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
