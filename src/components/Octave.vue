<template>
   <div class="octave">
           <Key v-bind:key="kei"  v-bind:kei="kei" v-for="kei in keys"/>
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
              pitch: 3,
              color: 'key--white',
              class: 'c' + this.pitch,
               isActive : false,
               hover : false,
               siblings: ['b' + (parseInt(this.pitch, 10)-1), 'c-sharp' + this.pitch, 'd' + this.pitch]
           },
           {
              name: 'C#' + this.pitch,
              pitch: 3,
              color: 'key--black',
              class: 'c-sharp' + this.pitch,
               isActive : false,
               hover : false,
               siblings: ['c' + this.pitch, 'd' + this.pitch]
           },
           { 
              name: 'D' + this.pitch,
              pitch: 3,
              color: 'key--white',
              class: 'd' + this.pitch,
               isActive : false,
               hover : false,
               siblings: ['c' + this.pitch, 'c-sharp' + this.pitch, 'd-sharp' + this.pitch, 'e' + this.pitch]
           },
           {
              name: 'D#' + this.pitch,
              pitch: 3,
              color: 'key--black',
              class: 'd-sharp' + this.pitch,
               isActive : false,
               hover : false,
               siblings: ['d' + this.pitch, 'e' + this.pitch]

           },
           { 
              name: 'E' + this.pitch,
              pitch: 3,
              color: 'key--white',
              class: 'e' + this.pitch,
               isActive : false,
               hover : false,
               siblings: ['d' + this.pitch, 'd-sharp' + this.pitch, 'f' + this.pitch]
           },
           { 
              name: 'F' + this.pitch,
              pitch: 3,
              color: 'key--white',
              class: 'f' + this.pitch,
               isActive : false,
               hover : false,
               siblings: ['e' + this.pitch, 'f-sharp' + this.pitch, 'g' + this.pitch]
           },
           {
              name: 'F#' + this.pitch,
              pitch: 3,
              color: 'key--black',
              class: 'f-sharp' + this.pitch,
               isActive : false,
               hover : false,
               siblings: ['f' + this.pitch, 'g' + this.pitch]
           },
           { 
              name: 'G' + this.pitch,
              pitch: 3,
              color: 'key--white',
              class: 'g' + this.pitch,
               isActive : false,
               hover : false,
               siblings: ['f' + this.pitch, 'f-sharp' + this.pitch, 'g-sharp' + this.pitch, 'a' + this.pitch]
           },
           {
              name: 'G#' + this.pitch,
              pitch: 3,
              color: 'key--black',
              class: 'g-sharp' + this.pitch,
               isActive : false,
               hover : false,
               siblings: ['g' + this.pitch, 'a' + this.pitch]
           },
           { 
              name: 'A' + this.pitch,
              pitch: 3,
              color: 'key--white',
              class: 'a' + this.pitch,
               isActive : false,
               hover : false,
               siblings: ['g' + this.pitch, 'g-sharp' + this.pitch, 'a-sharp' + this.pitch, 'b' + this.pitch]
           },
           {
              name: 'A#' + this.pitch,
              pitch: 3,
              color: 'key--black',
              class: 'a-sharp' + this.pitch,
               isActive : false,
               hover : false,
               siblings: ['a' + this.pitch, 'b' + this.pitch]
           },
           { 
              name: 'B' + this.pitch,
              pitch: 3,
              color: 'key--white',
              class: 'b' + this.pitch,
               isActive : false,
               hover : false,
               siblings: ['a' + this.pitch, 'a-sharp' + this.pitch, 'c' + (parseInt(this.pitch, 10)+1)]
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
    height: 50%;
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
        width: 50%;
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
