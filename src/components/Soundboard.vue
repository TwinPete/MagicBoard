<template>
    <div class="soundboard"
         v-bind:class="{soundboardactive: soundboard }"
    >
        <Soundbutton v-bind:key="soundbutton"  v-bind:soundbutton="soundbutton" v-for="soundbutton in soundbuttons"/>
    </div>
</template>

<script>
    import Soundbutton from './Soundbutton.vue'


    export default {
        name: 'Soundboard',
        components: {
            Soundbutton
        },
        props: ['soundboardActive'],
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

                ]
            }
        },
        methods: {
            push(){
                this.soundboardActive = !this.soundboardActive;
            }
        },
        mounted:  function mounted() {
            this.$root.$on('clickedSomething', function() {
                document.querySelector('.soundboard').classList.add('soundboardactive');
            })
        }
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
        display: none;
        position: absolute;
        left: 0;
        height: 100%;
        background-color: hotpink;
        transform: translateY(-110%);
        width: 100%;
        z-index: 9;
        top: 0;
    }

    .soundboardactive{
        display: flex;
        justify-content: space-evenly;
        flex-direction: column;
        transform: translateY(0);
        transition: transform ease 0.8s;
    }

    @media only screen and (min-width: 900px) {
        .soundboardactive{
            flex-direction: row;
        }
    }
</style>
