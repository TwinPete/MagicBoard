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
              class: 'c',
               isActive : 'key--white--inactive',
               siblings: ['b', 'c-sharp', 'd']
           },
           {
              name: 'C#',
              pitch: 3,
              color: 'key--black',
              class: 'c-sharp',
               isActive : 'key--black--inactive',
               siblings: ['c', 'd']
           },
           { 
              name: 'D',
              pitch: 3,
              color: 'key--white',
              class: 'd',
               isActive : 'key--white--inactive',
               siblings: ['c', 'c-sharp', 'd-sharp', 'e']
           },
           {
              name: 'D#',
              pitch: 3,
              color: 'key--black',
              class: 'd-sharp',
               isActive : 'key--white--inactive',
               siblings: ['d', 'e']

           },
           { 
              name: 'E',
              pitch: 3,
              color: 'key--white',
              class: 'e',
               isActive : 'key--white--inactive',
               siblings: ['d', 'd-sharp', 'f']
           },
           { 
              name: 'F',
              pitch: 3,
              color: 'key--white',
              class: 'f',
               isActive : 'key--white--inactive',
               siblings: ['e', 'f-sharp', 'g']
           },
           {
              name: 'F#',
              pitch: 3,
              color: 'key--black',
              class: 'f-sharp',
               isActive : 'key--white--inactive'
           },
           { 
              name: 'G',
              pitch: 3,
              color: 'key--white',
              class: 'g',
               isActive : 'key--white--inactive'
           },
           {
              name: 'G#',
              pitch: 3,
              color: 'key--black',
              class: 'g-sharp',
               isActive : 'key--white--inactive'
           },
           { 
              name: 'A',
              pitch: 3,
              color: 'key--white',
              class: 'a',
               isActive : 'key--white--inactive'
           },
           {
              name: 'A#',
              pitch: 3,
              color: 'key--black',
              class: 'a-sharp',
               isActive : 'key--white--inactive'
           },
           { 
              name: 'B',
              pitch: 3,
              color: 'key--white',
              class: 'b',
               isActive : 'key--white--inactive'
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
