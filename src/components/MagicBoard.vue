<template>
      <div class="magicboard">
        <Toolbar v-on:clickedSomething="switchBoard" v-bind:soundboardActive='soundboardActive'/>
        <div class="frame">
          <div class="wrapper">
              <Soundboard  v-bind:soundboardActive='soundboardActive' />
            <Keyboard />
          </div>
      </div> 
      </div>
</template>

<script>
import Toolbar from './Toolbar.vue'
import Keyboard from './Keyboard.vue'
import Soundboard from './Soundboard.vue'

export default {
  name: 'MagicBoard',
  components: {
    Toolbar,
    Keyboard,
      Soundboard
  },
  props: {
    
  },
    data(){
        return{
            soundboardActive: false
        }
    },
    methods: {
        handleClickInParent: function(){
            this.soundboardActive = !this.soundboardActive;
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
    
}
</style>
