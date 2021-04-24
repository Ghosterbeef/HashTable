<template>
    <div class="table-section">
        <div class="container">
            <div class="table">
                <div class="table-header">
                    <h3 class="key-value">id</h3>
                    <h3>Фамилия</h3>
                    <h3>Имя</h3>
                    <h3>Отчество</h3>
                    <h3>Группа</h3>
                    <div class="plug"></div>
                </div>
                <div class="table-body">
                    <Table_element></Table_element>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import Table_element from './Table_element'

    export default {
        name: "Table",
        components: {
            Table_element
        }
    }
</script>


<style scoped>
    .table-section {
        display: flex;
        justify-content: center;
    }

    .table {
        display: grid;
        grid-template-rows: max-content 1fr;
        justify-content: center;
        align-items: center;
        border: 2px solid black;
    }

    .table-header {
        display: grid;
        grid-template-columns: minmax(20px, max-content) repeat(4, minmax(60px, 200px)) 1fr;
        border-bottom: 2px solid black;
    }

    h3 {
        border-left: 2px solid black;
        text-align: center;
        padding: 5px 20px;
    }

    .plug{
        border-left: 2px solid black;
        width: 20px;
    }

    .key-value {
        border: none;
        text-align: left;
        width: 61px;
    }

    .table-body {
        min-height: 50vh;
        max-height: 50vh;
        overflow-y: scroll;
    }


    @media (max-width: 570px){
        h3{
            padding: 0;
            font-size: 0.9rem;
        }

        .key-value{
            text-align: center;
            padding: 0;
            width: 20px;
        }
    }

</style>