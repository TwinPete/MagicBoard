<template>
  <div id="app">
    <!--<div id="nav">-->
      <!--<router-link to="/">Home</router-link> |-->
      <!--<router-link to="/about">About</router-link>-->
    <!--</div>-->
    <router-view/>

    <!--<ion-app>-->

      <!--<ion-vue-router />-->
    <!--</ion-app>-->
  </div>
</template>

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
