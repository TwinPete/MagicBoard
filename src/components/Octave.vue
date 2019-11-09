<template>
   <div class="octave">
           <Key v-bind:key="kei.name"  v-bind:kei="kei" v-for="kei in keys"/>
   </div>
</template>

<script>
import Key from './Key.vue'

export default {
  name: 'Keyboard',
  components: {
    Key
  },
  props:['pitch'],
  data() {
      return{
          keys: [
           { 
              name: 'C' + this.pitch ,
              pitch: this.pitch,
              color: 'key--white',
              class: 'c' + this.pitch,
               isActive : false
           },
           {
              name: 'C#' + this.pitch,
              pitch: this.pitch,
              color: 'key--black',
              class: 'c-sharp' + this.pitch,
               isActive : false,
           },
           { 
              name: 'D' + this.pitch,
              pitch: this.pitch,
              color: 'key--white',
              class: 'd' + this.pitch,
               isActive : false,
           },
           {
              name: 'D#' + this.pitch,
              pitch: this.pitch,
              color: 'key--black',
              class: 'd-sharp' + this.pitch,
               isActive : false,

           },
           { 
              name: 'E' + this.pitch,
              pitch: this.pitch,
              color: 'key--white',
              class: 'e' + this.pitch,
               isActive : false,
           },
           { 
              name: 'F' + this.pitch,
              pitch: this.pitch,
              color: 'key--white',
              class: 'f' + this.pitch,
               isActive : false,
           },
           {
              name: 'F#' + this.pitch,
              pitch: this.pitch,
              color: 'key--black',
              class: 'f-sharp' + this.pitch,
               isActive : false,
           },
           { 
              name: 'G' + this.pitch,
              pitch: this.pitch,
              color: 'key--white',
              class: 'g' + this.pitch,
               isActive : false,
           },
           {
              name: 'G#' + this.pitch,
              pitch: this.pitch,
              color: 'key--black',
              class: 'g-sharp' + this.pitch,
               isActive : false,
           },
           { 
              name: 'A' + this.pitch,
              pitch: this.pitch,
              color: 'key--white',
              class: 'a' + this.pitch,
               isActive : false,
           },
           {
              name: 'A#' + this.pitch,
              pitch: this.pitch,
              color: 'key--black',
              class: 'a-sharp' + this.pitch,
               isActive : false,
           },
           { 
              name: 'B' + this.pitch,
              pitch: this.pitch,
              color: 'key--white',
              class: 'b' + this.pitch,
               isActive : false,
           },
      ]
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.octave{
    position: relative;
    width: 100%;
    /*height: 50%;*/
    min-height: 50%;
    max-height: 50%;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    justify-content: space-between;
    background-color: #666;
    z-index: 2;
}

.octave:first-of-type{
    border-bottom: solid 0.5px  transparent;
}

@media only screen and (min-width: 900px){
  
    .octave{
        min-width: 50%;
        max-width: 50%;
        min-height: unset;
        max-height: none;
        height: 100%;
        flex-direction: row;
        align-items: flex-start;
        justify-content: flex-start;
    }

    .octave:first-of-type{
        border-bottom: none;
        /*border-right: solid 0.6px  transparent;*/
    }
}
</style>
