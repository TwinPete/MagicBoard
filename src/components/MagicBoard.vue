<template>
      <div class="wrapper">
        <Toolbar />        
        <div class="magicboard">
          <div class="frame">
            <Keyboard /> 
          </div>
      </div> 
      </div>
</template>

<script>
import Toolbar from './Toolbar.vue'
import Keyboard from './Keyboard.vue'

export default {
  name: 'MagicBoard',
  components: {
    Toolbar,
    Keyboard
  },
  props: {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.wrapper{
    width: 100%;
    display: flex;
    flex-direction: row-reverse;
    height: 90vw;
    justify-content: center;
}
.magicboard{
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

  .frame{
    position: relative;
    width: 100%;
    height: 100%;
    max-width: 55vh;
    overflow: hidden;
}

@media only screen and (min-width: 900px){
  .wrapper{
    width: auto;
    flex-direction: column;
    height: auto;
}
  .frame{
        position: relative;
        width: 90vw;
        height: 30vw;
        max-height: 440px;
        max-width: 1400px;
    }
  .magicboard{
        width: 96%;
        height: 30vw;
        max-height: 440px;
        max-width: 1400px;
  }
    
}
</style>
