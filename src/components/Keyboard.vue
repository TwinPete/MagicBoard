<template>
   <div class="keyboard" v-on:mouseleave="resetKeyboard()">
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
       <div class="keyboard__customizer" v-bind:class="{keyboard__customizerActive: (!soundboardActive && editActive)}">
           <div class="keyboardOptions">
               <div class="keyboardOption"
                    v-bind:key="option" v-for="option in keyboardOptions"
                    v-on:click="function(){
                         option.isActive = true;
                    }"
               >
                   <div class="optionName">{{ option.name }}</div>
                   <div class="optionChecker">
                       <div class="led" v-bind:active="option.isActive"   v-bind:class="{ledActive: option.isActive }"></div>
                   </div>
               </div>
           </div>
       </div>
   </div>
</template>

<script>
import Octave from './Octave.vue'

export default {
  name: 'Keyboard',
  components: {
    Octave
  },
  props: ['soundboardActive', 'editActive', 'currentOctaveSlide', 'option'],
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
          ],
          keyboardOptions: [
              {
                  id: 1,
                  name: 'Piano',
                  isActive: true
              },
              {
                  id: 2,
                  name: 'Organ',
                  isActive: false
              },
              {
                  id: 3,
                  name: 'Synth',
                  isActive: false
              },
              {
                  id: 4,
                  name: 'bells',
                  isActive: false
              },
              {
                  id: 5,
                  name: 'marimba',
                  isActive: false
              },
              {
                  id: 6,
                  name: 'Hammond-Organ',
                  isActive: false
              },
              {
                  id: 7,
                  name: 'flute',
                  isActive: false
              },
          ]
      }
  },
    methods: {

        resetKeyboard(){
            document.querySelector('.keyboard').classList.remove('hover');
        },

      selectStyle(){
            // with this function the user selects the style the keyboard plays
          alert(this.option);
          this.option.isActive = !this.option.isActive;
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
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    transform: translateY(-120%);
    transition: transform ease 0.8s;
    background-color: #f4f4f4;
    border-bottom: #9f9f9f solid 1px;
    z-index: 9;
}

.keyboardOptions{
    width: calc(100% - 40px);
    height: calc(100% - 40px);
    /*border: solid 1px #333;*/
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
}

.keyboardOption{
    display: flex;
    border-radius: 3px;
    background-color: #333333;
    height: 40px;
    margin-right: 10px;
}

.optionName{
    display: flex;
    align-items: center;
    padding: 10px 10px 10px 30px;
    font-size: 16px;
    color: #fff;
    background-color: #333333;
    text-align: center;
    height: 20px;
    font-family: 'Roboto', sans-serif;
    border-radius: 3px;
}

.optionChecker{
    display: flex;
    align-items: center;
    width: 36px;
    height: 40px;
    border-radius: 3px;
}

.led{
    width: 20px;
    height: 20px;
    background-color: #444444;
}

.ledActive{
    background-color: #52d97f;
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
