<template>
      <div class="magicboard">
          <div class="toolbar" >
              <div class="options">
                  <div class="circle" v-on:click="openEdit()">Edit</div>
                  <div class="circle" v-on:click="prevOctave()">Prev</div>
                  <div class="circle circleCounter"><span class="sliderCount"> C{{ (currentOctaveSlide + 1) }} - B{{ (currentOctaveSlide + 2) }} </span></div>
                  <div class="circle" v-on:click="nextOctave()">Next</div>
              </div>
              <div class="switch">
                  <div class="circle" v-on:click="switchBoard()">
                      <div class="boardName" v-if="!soundboardActive">Soundboard</div>
                      <div class="boardName" v-else>Keyboard</div>
                  </div>
              </div>
          </div>
        <div class="frame">
          <div class="wrapper">
              <Soundboard v-bind:editActive='editActive' v-bind:soundboardActive='soundboardActive' />
              <Keyboard v-bind:editActive='editActive' v-bind:soundboardActive='soundboardActive' v-bind:currentOctaveSlide='currentOctaveSlide' />
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
            editActive: false,
            currentOctaveSlide: 2
        }
    },
    methods:{
        switchBoard(){
            this.soundboardActive = !this.soundboardActive;
            this.editActive = false;
        },
        openEdit(){
            this.editActive = !this.editActive;
        },
        prevOctave(){
            if(this.currentOctaveSlide > 0){
                this.currentOctaveSlide -= 1;
            }
        },
        nextOctave(){
            if(this.currentOctaveSlide < 5){
                this.currentOctaveSlide += 1;
            }
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
    width: auto;
    height: calc(100vh - 4%);
    display: flex;
    justify-content: space-between;
    flex-direction: row;
    align-items: flex-start;
    padding: 20px 1px;
    writing-mode: vertical-lr;
}

.options{
    display: flex;
    justify-content: space-between;
}

.circle{
    position: relative;
    padding: 5px;
    font-size: 1.2rem;
    color: #fff;
    text-align: center;
    background-color: #333;
    margin-left: 5px;
    border-radius: 1px;
    font-family: sans-serif;
    /*height: 115px;*/
    min-height: 50px;
    width: auto;
    margin-bottom: 10px;
}

.circleCounter{
    min-width: auto;
    min-height: 115px;
}

/*.circle:nth-child(2){*/
    /*min-height: 115px;*/
/*}*/

.sliderCount{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

.switch{
    position: relative;
    height: auto ;
}

.switch .circle{
    height: 160px;
    width: 1.8rem;
}


.boardName{
    width: 1.8rem;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

@media only screen and (min-width: 1281px) {

    .magicboard{
        margin-top: 80px;
    }

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
        width: 96%;
        padding: 2%;
        height: auto;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        writing-mode: horizontal-tb;
    }
    .options{
        width:30%;
    }
    .circle{
        font-size: 1.8rem;
        margin-left: 10px;
        min-width: 100px;
        text-align: center;
        height: auto;
        margin-bottom: 0;
        min-height: auto;
        padding: 10px;

    }

    .circleCounter{
        min-width: 115px;
        min-height: auto;
    }

    .circle:not(.slideCount){
        cursor: pointer;
    }

    .switch{
        position: relative;
        height:38px;
    }


    .switch .circle{
        width: 160px;
        height: 1.8rem;
    }

    .boardName{
        width: 200px;
    }




    
}

@media only screen and (max-width: 500px){
    .circle{
        min-height: 35px!important;
    }

    .circleCounter{
        min-height: 75px!important;
    }

    .switch .circle{
        height: 100px;
        margin-bottom: 25px;
    }
}
</style>
