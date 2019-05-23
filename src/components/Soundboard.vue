<template>
    <div class="soundboard"
         v-bind:class="{soundboardactive: soundboardActive }"
    >
        <Soundbutton v-bind:key="soundbutton"  v-bind:soundbutton="soundbutton" v-for="soundbutton in soundbuttons"/>
        <div class="soundboard__customizer" v-bind:class="{soundboard__customizerActive: (soundboardActive && editActive)}">
            <div class="fileInput" v-bind:key="audioFiles" v-for="audioFiles in audioFiles">
                <input type="file">
            </div>
        </div>
    </div>
</template>

<script>
    import Soundbutton from './Soundbutton.vue'


    export default {
        name: 'Soundboard',
        components: {
            Soundbutton
        },
        props: ['soundboardActive', 'editActive'],
        data(){
            return{
                soundboard: false,
                soundbuttons: [
                    {
                        title: 'btn1'
                    },
                    {
                        title: 'btn2'
                    },
                    {
                        title: 'btn3'
                    },
                    {
                        title: 'btn4'
                    },
                    {
                        title: 'btn5'
                    },
                    {
                        title: 'btn6'
                    },
                    {
                        title: 'btn7'
                    },
                    {
                        title: 'btn8'
                    },
                    {
                        title: 'btn9'
                    },
                    {
                        title: 'btn10'
                    },

                ],
                audioFiles: [
                    {
                        title: 'btn1'
                    },
                    {
                        title: 'btn2'
                    },
                    {
                        title: 'btn3'
                    },
                    {
                        title: 'btn4'
                    },
                    {
                        title: 'btn5'
                    },
                    {
                        title: 'btn6'
                    },
                    {
                        title: 'btn7'
                    },
                    {
                        title: 'btn8'
                    },
                    {
                        title: 'btn9'
                    },
                    {
                        title: 'btn10'
                    },

                ]
            }
        },
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

    .btn{
        position: fixed;
        top: 10px;
        left: 10px;
        width: 50px;
        height: 50px;
    }

    .soundboard{
        display: flex;
        position: absolute;
        left: 0;
        height: 100%;
        background-color: hotpink;
        transform: translateY(-110%);
        transition: transform ease 0.8s;
        width: 100%;
        z-index: 9;
        top: 0;
    }

    .soundboardactive{
        justify-content: space-evenly;
        flex-direction: column;
        transform: translateY(0);
    }

    .soundboard__customizer{
        position: absolute;
        top: 0;
        left: 0;
        display: flex;
        flex-direction: column;
        width: 100%;
        height: 100%;
        transform: translateY(-120%);
        transition: transform ease 0.8s;
        background-color: #444444;
        z-index: 9;
    }

    .fileInput{
        display: flex;
        width: 100%;
        height: 10%;
        border-right: 1px solid #333;
        border-bottom: 1px solid #333;
    }

    .soundboard__customizerActive{
        transform: translateY(0);
    }

    @media only screen and (min-width: 900px) {
        .soundboardactive{
            flex-direction: row;
        }
        .soundboard__customizer{
            flex-direction: row;
        }
        .fileInput{
            width: 10%;
            height: 100%;
        }
    }
</style>
