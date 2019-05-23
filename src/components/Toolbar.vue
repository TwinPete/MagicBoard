<template>
    <div class="toolbar"
         v-on:click="switchBoard()"
    >
        <div class="options">
            <div class="circle">button</div>
            <div class="circle">dfh</div>
            <div class="circle">fgjd</div>
        </div>
        <div class="switch">
            <div class="circle">
                <div v-if="soundboardActive">Soundboard</div>
                <div v-else>Keyboard</div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Toolbar',
  props: ['soundboardActive'],
    methods:{
        switchBoard(){
            this.soundboardActive = !this.soundboardActive;
            this.$root.$emit('clickedSomething');
        }

    }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .toolbar{
        width: 10%;
        height:  100vh;
        display: flex;
        justify-content: flex-start;
        flex-direction: column;
        align-items: flex-start;
        padding: 20px;
        writing-mode: vertical-lr;
    }
    .circle{
        padding: 10px 20px;
        font-size: 1.8rem;
        color: #fff;
        background-color: #333;
        margin-left: 5px;
        border-radius: 1px;
        font-family: sans-serif;
        height: 100px;
        margin-bottom: 10px;
    }
    @media only screen and (min-width: 900px){
        .toolbar{
            width: calc(100% - 40px);
            height: auto;
            flex-direction: row;
            justify-content: flex-start;
            align-items: center;
            writing-mode: horizontal-tb;
        }
        .circle{
            margin-left: 10px;
            min-width: 100px;
            text-align: center;
            height: auto;
            margin-bottom: 0;
        }
    }
</style>
