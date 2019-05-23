<template>
   <div
            class="key"
            draggable="false"
            v-bind:class="[kei.color, kei.class, {active: kei.isActive}]"
            v-on:mousedown="playKey()"
            v-on:mouseleave="leaveKey()"
            v-on:mouseup="releaseKey()"
            v-on:mouseover="slide()"
   >
      <div class="key__name">
         {{ kei.name }}
      </div>
   </div>
</template>

<script>

export default {
  name: 'Key',
  components: {
  },
  props: ['kei'],
   methods:{
     playKey(){
        this.kei.isActive = true;
         document.querySelector('.keyboard').classList.add('hover');

     },
      releaseKey(){
         this.kei.isActive = false;
         document.querySelector('.keyboard').classList.remove('hover');
         },
      leaveKey(){
         this.kei.isActive = false;
      },
      slide(){
         let hoverModeActive = document.querySelector('.keyboard').classList.contains('hover');
         if( hoverModeActive){
            this.kei.isActive = true;
         }
      }
   }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.key{
   display: flex;
   align-items: center;
   justify-content: flex-start;
   -webkit-user-drag: none;
   -khtml-user-drag: none;
   -moz-user-drag: none;
   -o-user-drag: none;
   user-drag: none;
   -webkit-user-select: none;
   -khtml-user-select: none;
   -moz-user-select: none;
   -o-user-select: none;
   user-select: none;
}

.key__name{
   display: none;
   font-size: 13px;
   font-family: 'Roboto', sans-serif;
   text-align: center;
   margin-left: 20px;
   writing-mode: vertical-lr;
}

.key--white{
    width: 100%;
    height: 14.08% ;
    background-color: #fff;
    box-shadow: 1px 1px 1px 1px #666;
    border-bottom: 0.8px solid #555;
    display: flex;
    border-radius: 4px;
    z-index: 6;
    transition: width ease 0.3s;
}

.key--white.active{
    background-color: palegreen!important;
    z-index: 4;
    width: 98%!important;
}

.key--black{
    position: absolute;
    width: 70%;
    height: 10.08%;
    background-color: #222;
    z-index: 9;
    border-radius: 5px;
    right: -2px;
    border-bottom: solid 0.7px #222;
    transition: width ease 0.7s;
    box-shadow: 1px 1px 1px 1px #444;
}

.key--black .key__name{
   color: #fff;
}

.key--black.active{
    background-color: paleturquoise!important;
    z-index: 7;
    width: 69.5%!important;
}

.c-sharp1, .c-sharp2, .c-sharp3, .c-sharp4, .c-sharp5, .c-sharp6, .c-sharp7{
    top: 8%;
}

.d-sharp1, .d-sharp2, .d-sharp3, .d-sharp4, .d-sharp5, .d-sharp6, .d-sharp7{
    top: 24%;
}

.f-sharp1, .f-sharp2, .f-sharp3, .f-sharp4, .f-sharp5, .f-sharp6, .f-sharp7{
    top: 51%;
}

.g-sharp1, .g-sharp2, .g-sharp3, .g-sharp4, .g-sharp5, .g-sharp6, .g-sharp7{
    top: 66%;
}

.a-sharp1, .a-sharp2, .a-sharp3, .a-sharp4, .a-sharp5, .a-sharp6, .a-sharp7{
    top: 82%;
}

/* .octave:first-of-type .b:last-child{
    border-bottom: none;
} */

@media only screen and (min-width: 900px){

   .key{
      align-items: flex-end;
      justify-content: center;
   }

   .key__name{
      margin-bottom: 20px;
      margin-left: 0;
      writing-mode: horizontal-tb;
      font-size: 15px;
   }

  .key--white{
        width: 14.2857142857%;
        height: 100%;
        background-color: #fff;
        box-shadow: 1px 1px 1px 1px #999;
        border-right: 0.8px solid #555;
        display: flex;
        border-radius: 4px;
        transition: height ease 0.3s;
    }

    .key--white.active{
        background-color: palegreen!important;
        z-index: 4;
        height: 98%!important;
        width: 14.2857142857%!important;
    }

    .key--black.active{
        background-color: paleturquoise!important;
        z-index: 7;
        height: 69.5%!important;
        width: 8%!important;
    }

    .key--black{
        height: 70%;
        width: 8%;
        top: -2px;
        transition: height ease 0.3s;
    }

   .c-sharp1, .c-sharp2, .c-sharp3, .c-sharp4, .c-sharp5, .c-sharp6, .c-sharp7{
        left: 9%;

    }

   .d-sharp1, .d-sharp2, .d-sharp3, .d-sharp4, .d-sharp5, .d-sharp6, .d-sharp7{
        left: 26%;
    }

   .f-sharp1, .f-sharp2, .f-sharp3, .f-sharp4, .f-sharp5, .f-sharp6, .f-sharp7{
        left: 52%;
    }

   .g-sharp1, .g-sharp2, .g-sharp3, .g-sharp4, .g-sharp5, .g-sharp6, .g-sharp7{
        left: 67.3%;
    }

   .a-sharp1, .a-sharp2, .a-sharp3, .a-sharp4, .a-sharp5, .a-sharp6, .a-sharp7{
        left: 82.5%;
    }
    
}
</style>
