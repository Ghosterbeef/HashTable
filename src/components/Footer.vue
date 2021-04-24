<template>
    <footer>
        <div class="container">
            <p>Разработал <a href="https://github.com/Ghosterbeef" class="signature" target="_blank">Ghosterbeef</a> по гайдам в <span class="rofl">ВАШИХ ИНТЕРНЕТАХ</span>!
            </p>
            <p>Разработано с помошью фреймворка <a href="https://vuejs.org/" target="_blank">Vue.js</a>. Спасибо <a href="https://github.com/yyx990803/" target="_blank">Эван Ю!</a></p>
            <p v-if="getCurrentYear===2021">2021</p>
            <p v-else>2021 - {{getCurrentYear}}</p>
        </div>
    </footer>
</template>

<script>
    export default {
        name: "Footer",
        computed:{
            getCurrentYear: function () {
                let date = new Date()
                return date.getFullYear()
            }
        }
    }
</script>


<style scoped>
    footer {
        display: flex;
        justify-content: center;
        background-color: dimgrey;
        font-family: 'Jura', sans-serif;
        color: white;
        padding: 20px 0;
        font-weight: bold;
    }

    footer a {
        color: #2c3e50;
        font-family: 'Balsamiq Sans', cursive;
    }

    footer .rofl {
        font-family: 'Balsamiq Sans', cursive;
        font-size: 0.8rem;
    }
</style>