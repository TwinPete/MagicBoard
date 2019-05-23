<template>
      <div class="magicboard">
          <div class="toolbar" >
              <div class="options">
                  <div class="circle" v-on:click="openEdit()">Edit</div>
                  <div class="circle">dfh</div>
                  <div class="circle">fgjd</div>
              </div>
              <div class="switch">
                  <div class="circle" v-on:click="switchBoard()">
                      <div v-if="soundboardActive">Soundboard</div>
                      <div v-else>Keyboard</div>
                  </div>
              </div>
          </div>
        <div class="frame">
          <div class="wrapper">
              <Soundboard v-bind:editActive='editActive' v-bind:soundboardActive='soundboardActive' />
              <Keyboard v-bind:editActive='editActive' v-bind:soundboardActive='soundboardActive' />

          </div>
      </div> 
      </div>
</template>

<script>
import Keyboard from './Keyboard.vue'
import Soundboard from './Soundboard.vue'

export default {
  name: 'MagicBoard',
  components: {
    Keyboard,
      Soundboard
  },
  props: {
    
  },
    data(){
        return{
            soundboardActive: false,
            editActive: false
        }
    },
    methods:{
        switchBoard(){
            this.soundboardActive = !this.soundboardActive;
            this.editActive = false;
        },
        openEdit(){
            this.editActive = !this.editActive;
        }

    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.magicboard{
    width: 100%;
    display: flex;
    flex-direction: row-reverse;
    height: 90vw;
    justify-content: center;
}
.frame{
    position: relative;
    width: 96%;
    max-width: 55vh;
    height: calc(100vh - 4%);
    background-color: #e0dbd8;
    padding: 2%;
    display: flex;
    justify-content: center;
    align-items: center;
}

  .wrapper{
    position: relative;
    width: 100%;
    height: 100%;
    max-width: 55vh;
    overflow: hidden;
}

.toolbar{
    width: 10%;
    height:  100vh;
    display: flex;
    justify-content: flex-start;
    flex-direction: column;
    align-items: flex-start;
    padding: 20px;
    writing-mode: vertical-lr;
}
.circle{
    padding: 10px 20px;
    font-size: 1.8rem;
    color: #fff;
    background-color: #333;
    margin-left: 5px;
    border-radius: 1px;
    font-family: sans-serif;
    height: 100px;
    margin-bottom: 10px;
}








@media only screen and (min-width: 900px){
  .magicboard{
    width: auto;
    flex-direction: column;
    height: auto;
}
  .wrapper{
        position: relative;
        width: 90vw;
        height: 30vw;
        max-height: 440px;
        max-width: 1400px;
    }
  .frame{
        width: 96%;
        height: 30vw;
        max-height: 440px;
        max-width: 1400px;
  }

    .toolbar{
        width: calc(100% - 40px);
        height: auto;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        writing-mode: horizontal-tb;
    }
    .circle{
        margin-left: 10px;
        min-width: 100px;
        text-align: center;
        height: auto;
        margin-bottom: 0;
    }
    
}
</style>
