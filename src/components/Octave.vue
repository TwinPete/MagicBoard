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
  props:{},
  data() {
      return{
          keys: [
           { 
              name: 'C',
              pitch: 3,
              color: 'key--white',
              class: 'c'
           },
           {
              name: 'C#',
              pitch: 3,
              color: 'key--black',
              class: 'c-sharp'
           },
           { 
              key: 'D',
              pitch: 3,
              color: 'key--white',
              class: 'd'
           },
           {
              name: 'D#',
              pitch: 3,
              color: 'key--black',
              class: 'd-sharp'
           },
           { 
              name: 'E',
              pitch: 3,
              color: 'key--white',
              class: 'e'
           },
           { 
              name: 'F',
              pitch: 3,
              color: 'key--white',
              class: 'f'
           },
           {
              name: 'F#',
              pitch: 3,
              color: 'key--black',
              class: 'f-sharp'
           },
           { 
              name: 'G',
              pitch: 3,
              color: 'key--white',
              class: 'g'
           },
           {
              name: 'G#',
              pitch: 3,
              color: 'key--black',
              class: 'g-sharp'
           },
           { 
              name: 'A',
              pitch: 3,
              color: 'key--white',
              class: 'a'
           },
           {
              name: 'A#',
              pitch: 3,
              color: 'key--black',
              class: 'a-sharp'
           },
           { 
              name: 'B',
              pitch: 3,
              color: 'key--white',
              class: 'b'
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
