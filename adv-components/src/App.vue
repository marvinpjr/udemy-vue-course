<template>
  <div id="app">   
    <div class="row">
        <div class="col-md"><button class="btn btn-primary" @click="loadComponent('blue')">Load Blue Template</button></div>
        <div class="col-md"><button class="btn btn-success" @click="loadComponent('green')">Load Green Template</button></div>
        <div class="col-md"><button class="btn btn-danger" @click="loadComponent('red')">Load Red Template</button></div>
    </div> 
    <keep-alive>
      <component :is="selectedComponent">
          {{ selectedComponent }} Component
          <p slot="part2">Content only for part 2</p>
      </component>
    </keep-alive>
    
    <!-- <blue>
      <p>Give this to that blue slot.</p>
    </blue>
    <red>
      <p>The green slot is getting the content of this p.</p>
    </red>
    <green>
      <h3 slot="part1">Header for First Slot</h3>
      <p slot="part2">Paragraph text for Second Slot.</p>
    </green> -->
    
  </div>
</template>

<script>
import Blue from "./components/Blue";
import Red from "./components/Red";
import Green from "./components/Green";

export default {
  name: "app",
  components: {
    Blue,
    Red,
    Green
  },
  data: function() {
    return {
      selectedComponent: String
    };
  },
  methods: {
    loadComponent: function(componentName) {
      this.selectedComponent = componentName;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
