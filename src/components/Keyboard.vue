<template>
   <div class="keyboard">
       <Octave v-bind:pitch="octave.pitch" v-bind:key="index" v-for="(octave, index) in octaves" />
       <div class="keyboard__customizer" v-bind:class="{keyboard__customizerActive: (!soundboardActive && editActive)}"></div>
   </div>
</template>

<script>
import Octave from './Octave.vue'

export default {
  name: 'Keyboard',
  components: {
    Octave
  },
  props: ['soundboardActive', 'editActive'],
  data(){
      return{
          octaves: [
              {
                  pitch: 3
              },
              {
                  pitch: 4
              }
          ]
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.keyboard{
    position: absolute;
    left: 0;
    height: 100%;
    max-width: 55vh;
    background-color: lightslategrey;
    width: 100%;
    z-index: 1;
    top: 0;
}



.keyboard__customizerActive{
    transform: translateY(0);
}

.keyboard__customizer{
    position: absolute;
    top: 0;
    left: 0;
    display: flex;
    width: 100%;
    height: 100%;
    transform: translateY(-120%);
    transition: transform ease 0.8s;
    background-color: #9e383d;
    z-index: 9;
}

.keyboard__customizerActive{
    transform: translateY(0);
}

@media only screen and (min-width: 900px){
  
    .keyboard{
        position: absolute;
        width: 100%;
        height: 100%;
        max-width: none;
        display: flex;
        justify-content: center;
    }
}
</style>
