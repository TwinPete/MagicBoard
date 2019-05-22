<template>
    <div class="soundbutton">
            <div class="soundbutton__name">{{ this.soundbutton.title }}</div>
    </div>
</template>

<script>
    export default {
        name: "Soundbutton",
        props: ['soundbutton']
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
    }

    @media only screen and (min-width: 900px) {
        .soundbutton{
            height: 100%;
            width: 10%;
            display: flex;
            writing-mode: vertical-lr;
        }
    }

</style>