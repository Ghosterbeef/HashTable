<template>
    <div class="table-element">
        <p id="id" class="element-section">#</p>
        <p id="surname" class="element-section">Placeholder</p>
        <p id="name" class="element-section">Placeholder</p>
        <p id="patronymic" class="element-section">Placeholder</p>
        <p id="group" class="element-section">Placeholder</p>
    </div>
</template>

<script>
    export default {
        name: "Table_element",
    }
</script>


<style scoped>
    .table-element{
        display: grid;
        grid-template-columns: minmax(20px, max-content) repeat(4, minmax(60px, 200px));
        margin: 10px 2px;
        border: 1px solid black;
    }

    .element-section{
        text-align: center;
        border-left: 1px solid black;
        padding: 5px 0;
    }

    #id.element-section{
        width: 58px;
        border: none;
    }


    @media (max-width: 570px){
        .table-element{
            margin: 10px 0;
        }
        .element-section{
            padding: 0;
            font-size: 0.9rem;
        }

        #id.element-section{
            text-align: center;
            padding: 0;
            width: 20px;
        }
    }
</style>