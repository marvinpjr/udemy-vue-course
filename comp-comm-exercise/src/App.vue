<template>
  <div id="app">
    <div class="container">
    <header></header>
    <div class="row">
      <div class="col">
        <server-list></server-list>
      </div>
      <div class="col">
        <server-detail></server-detail>
      </div>
    </div>
    <footer></footer>  
    </div>    
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Header from "./components/shared/header";
import Footer from "./components/shared/footer";
import ServerList from "./components/server/serverlist";
import ServerDetail from './components/server/serverdetail';

export default {
  name: "app",
  components: {
    Header,
    Footer,
    ServerList,
    ServerDetail
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
