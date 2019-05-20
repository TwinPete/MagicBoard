<template>
    <div class="toolbar">
        <!-- <div class="circle">button</div>
        <div class="circle">dfh</div>
        <div class="circle">fgjd</div> -->
    </div>
</template>

<script>
export default {
  name: 'Toolbar',
  props: {
    
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
        padding: 10px;
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
            width: 100%;
            height: auto;
            flex-direction: row;
            justify-content: flex-start;
            align-items: center;
        }
        .circle{
            margin-left: 10px;
            min-width: 100px;
            text-align: center;
            writing-mode: horizontal-tb;
            height: auto;
            margin-bottom: 0;
        }
    }
</style>
