<template>
   <div
            class="key" v-bind:class="[kei.color, kei.class, kei.isActive]" v-on:mousedown="playKey()" v-on:mouseup="releaseKey()" v-on:mouseover="slide()">

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
        this.kei.isActive = this.kei.color + '--active';
        console.log(this.kei.siblings);
     },
      releaseKey(){

         this.kei.isActive = this.kei.color + '--inactive';
      },
      slide(){
         for (var key of this.kei.siblings) {
            // console.log(document.querySelector('.' + key).classList);
            if (document.querySelector('.' + key).classList.contains('key--white--active') || document.querySelector('.' + key).classList.contains('key--black--active')) {
               document.querySelector('.' + key).classList.remove('key--white--active');
               document.querySelector('.' + key).classList.remove('key--black--active');
               this.kei.isActive = this.kei.color + '--active';
               break;
            }
         }

      }
   }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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

.key--white--active{
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

.key--black--active{
    background-color: paleturquoise!important;
    z-index: 7;
    width: 68%!important;
}

.c-sharp{
    top: 8%;
}

.d-sharp{
    top: 24%;
}

.f-sharp{
    top: 51%;
}

.g-sharp{
    top: 66%;
}

.a-sharp{
    top: 82%;
}

/* .octave:first-of-type .b:last-child{
    border-bottom: none;
} */

@media only screen and (min-width: 900px){
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

    .key--white--active{
        background-color: palegreen!important;
        z-index: 4;
        height: 98%!important;
        width: 14.2857142857%!important;
    }

    .key--black--active{
        background-color: paleturquoise!important;
        z-index: 7;
        height: 68%!important;
        width: 8%!important;
    }

    .key--black{
        height: 70%;
        width: 8%;
        top: -2px;
        transition: height ease 0.3s;
    }

    .c-sharp{
        left: 9%;

    }

    .d-sharp{
        left: 26%;
    }

    .f-sharp{
        left: 52%;
    }

    .g-sharp{
        left: 67.3%;
    }

    .a-sharp{
        left: 82.5%;
    }
    
}
</style>
