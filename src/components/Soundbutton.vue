<template>
    <div class="soundbutton"
        @mousedown="play()"
        @mouseup="release()"
    >
            <div class="soundbutton__name">{{ this.soundbutton.title }}</div>
    </div>
</template>

<script>
    import Tone from 'tone'

    export default {
        name: "Soundbutton",
        props: ['soundbutton'],
        data(){
            return{
                synth: ''
            }
        },
        watch: {

        },
        methods: {
            initialiseSound(){
                this.synth = new Tone.Synth().toMaster();
            },
            play(){
                //play a middle 'C' for the duration of an 8th note
                this.synth.triggerAttackRelease(this.soundbutton.name, '8n');
            },
            release(){

            }
        },
        mounted (){

        }

    }

</script>

<style scoped>

    .soundbutton{
        display: flex;
        height: 22%;
        width: 100%;
        background-color: #fff;
        box-shadow: 1px 1px 1px 1px #777;
        align-items: center;
        justify-content: center;
        writing-mode: horizontal-tb;
        font-size: 18px;
        cursor: pointer;
    }

    .soundbutton:hover{
        background-color: #f4f4f4;
    }

    .soundbutton__name{
        font-family: 'Roboto', sans-serif;
    }


    @media only screen and (min-width: 900px) {
        .soundbutton{
            height: 100%;
            width: 10%;
            display: flex;
            writing-mode: vertical-lr;
        }
        .soundbutton__name{
            transform: matrix(-1, 0, 0, -1, 0, 0);
        }
    }

</style>