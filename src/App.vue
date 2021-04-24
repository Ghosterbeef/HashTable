<template>
    <Development_only></Development_only>
    <Header></Header>
    <Table></Table>
    <Control_buttons @addElement="addElement" @searchElement="searchElement" @delElement="delElement"></Control_buttons>
    <Footer></Footer>
</template>

<script>
    import Development_only from './components/developmentOnly'   //Удалить после окончания разработки

    import Header from './components/Header'
    import Footer from './components/Footer'
    import Table from  './components/Table'
    import Control_buttons from  './components/Control_buttons'

    export default {
        name: 'App',
        components: {
            Development_only, //Удалить после окончания разработки
            Header,
            Footer,
            Table,
            Control_buttons
        },
        methods:{
            addElement: function (Data) {
                console.log(Data)
            },
            searchElement: function (Data) {
                console.log(Data)
            },
            delElement: function (Data) {
                console.log(Data)
            }
        }
    }
</script>

<style>

    *, *::before, *::after {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
        user-select: none;
    }

    #app {
        min-height: 100vh;
        display: grid;
        grid-template-rows: max-content 1fr auto max-content;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
    }

    .container{
        min-width: 300px;
        max-width: 1200px;
    }



</style>

//font-family: 'Balsamiq Sans', cursive;
//font-family: 'Cormorant', serif;
//font-family: 'Jura', sans-serif;
//font-family: 'Press Start 2P', cursive;
//font-family: 'Stick', sans-serif;
