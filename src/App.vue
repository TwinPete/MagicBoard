<template>
  <div id="app">
    <Header />
    <MagicBoard />
  </div>
</template>

<script>
import MagicBoard from './components/MagicBoard.vue'
import Header from './components/Header.vue'

export default {
  name: 'app',
  components: {
    MagicBoard,
    Header
  }
}
</script>

<style>

*{
    margin: 0;
    padding: 0;
}
html{
  font-size: 10px;
}
ul{
    list-style: none;
}

a{
    text-decoration: none;
    color: inherit;
}

a:visited{
    color: inherit;
}
#app {
    width: 100%;
    height: 100vh;
    overflow: hidden;
}
@media only screen and (min-width: 900px){
  #app {
   display: fleX;
    align-items: center;
    justify-content: center;
}
}
</style>
