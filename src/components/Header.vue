<template>
    <div class="header">
        <div class="header__content">
            <div class="logo">
                <div class="image">
                    <img src="../assets/logo.png" alt="">
                </div>
            </div>
            <div class="auth">
                <div class="login">Login</div>
                <div class="registration">Register</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "header"
    }
</script>

<style scoped>

    .header{
        display: none;
        justify-content: center;
        position: fixed;
        left: 0;
        top: 0;
        width: 100%;
        height: 100px;
    }

    .header__content{
        display: flex;
        justify-content: space-between;
        width: 100%;
        max-width: 1440px;
    }

    .logo{
        width: 280px;
        height: calc(100% - 20px);
        padding: 10px;
        cursor: pointer;
    }

    .image{
        background-color: #9e383d;
        width: 100%;
        height: 100%;
        overflow: hidden;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .image img{
        width: 100%;
        height: 100%;
    }

    .auth{
        display: flex;
        justify-content: flex-end;
        align-items: center;
        width: 300px;
    }
    .login, .registration{
        margin-right: 20px;
        font-size: 18px;
        color: #333;
        font-family: 'Roboto', sans-serif;
        cursor: pointer;
    }


    @media only screen and (min-width: 900px) {

        .header{
            display: flex;
        }

    }

</style>