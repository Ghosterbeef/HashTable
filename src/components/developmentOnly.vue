<template>
    <div class="development-only">
        <h2>Development only!</h2>
        <h3>Font picker</h3>
        <p class="font">1 font-family: 'Balsamiq Sans', cursive;</p>
        <p class="font">2 font-family: 'Cormorant', serif;</p>
        <p class="font">3 font-family: 'Jura', sans-serif;</p>
        <p class="font">4 font-family: 'Press Start 2P', cursive;</p>
        <p class="font">5 font-family: 'Stick', sans-serif;</p>
    </div>
</template>

<script>
    export default {
        name: "Development_only",
    }
</script>


<style scoped>
    .development-only {
        top: 25%;
        right: 50px;
        position: fixed;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: space-evenly;
        width: 300px;
        min-height: 200px;
        border: 2px solid red;
        border-radius: 20px;
    }

    h2,h3{
        width: 100%;
        text-align: center;
    }

    p {
        text-align: left;
        user-select: text;
        font-weight: bold;
        color: black;
    }

    p:nth-child(3) {
        font-family: 'Balsamiq Sans', cursive;
    }

    p:nth-child(4) {
        font-family: 'Cormorant', serif;
    }

    p:nth-child(5) {
        font-family: 'Jura', sans-serif;
    }

    p:nth-child(6) {
        font-family: 'Press Start 2P', cursive;
        font-size: 0.55rem;
    }

    p:nth-child(7) {
        font-family: 'Stick', sans-serif;
    }
</style>