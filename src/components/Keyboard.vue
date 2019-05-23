<template>
   <div class="keyboard">
       <div class="slider" v-bind:class="[
       {slideZero: currentOctaveSlide == 0},
       {slideOne: currentOctaveSlide == 1},
       {slideTwo: currentOctaveSlide == 2},
       {slideThree: currentOctaveSlide == 3},
       {slideFour: currentOctaveSlide == 4},
       {slideFive: currentOctaveSlide == 5}
       ]">
           <Octave v-bind:pitch="octave.pitch" v-bind:key="index" v-for="(octave, index) in octaves" />
       </div>
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
  props: ['soundboardActive', 'editActive', 'currentOctaveSlide'],
  data(){
      return{
          octaves: [
              {
                  pitch: 1
              },
              {
                  pitch: 2
              },
              {
                  pitch: 3
              },
              {
                  pitch: 4
              },
              {
                  pitch: 5
              },
              {
                  pitch: 6
              },
              {
                  pitch: 7
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
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    background-color: lightslategrey;
    width: 100%;
    overflow: hidden;
    z-index: 1;
    top: 0;
}

.slider{
    display: flex;
    width: 100%;
    height: 100%;
    flex-direction: column;
    transition: transform ease-in-out 0.8s;
}

.slideZero{
    transform: translateY(0);
}

.slideOne{
    transform: translateY(-50%);
}

.slideTwo{
    transform: translateY(-100%);
}

.slideThree{
    transform: translateY(-150%);
}

.slideFour{
    transform: translateY(-200%);
}

.slideFive{
    transform: translateY(-250%);
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
        flex-direction: row;
        justify-content: center;
    }

    .slider{
        width: 100%;
        height: 100%;
        flex-direction: row;
    }

    .slideZero{
        transform: translateY(0);
        transform: translateX(0);
    }

    .slideOne{
        transform: translateY(0);
        transform: translateX(-50%);
    }

    .slideTwo{
        transform: translateY(0);
        transform: translateX(-100%);
    }

    .slideThree{
        transform: translateY(0);
        transform: translateX(-150%);
    }
    .slideFour{
        transform: translateY(0);
        transform: translateX(-200%);
    }
    .slideFive{
        transform: translateY(0);
        transform: translateX(-250%);
    }
}
</style>
