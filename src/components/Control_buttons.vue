<template>
    <div class="control-buttons-section">
        <div class="container">
            <div class="forms-container">
                <form id="insert-form" class="insert-form" @submit.prevent="addElement">
                    <input type="number" placeholder="id" v-model="addElementData.id">
                    <input type="text" placeholder="Фамилия" v-model="addElementData.surname">
                    <input type="text" placeholder="Имя" v-model="addElementData.name">
                    <input type="text" placeholder="Отчество" v-model="addElementData.patronymic">
                    <input type="text" placeholder="Группа" v-model="addElementData.group">
                    <input type="submit" value="Добавить" @click.prevent="addElement" @mouseup="deleteFocus">
                </form>
                <form id="search-form" class="search-form" @submit.prevent="searchElement">
                    <input type="number" placeholder="id" v-model="searchElementData.id">
                    <input type="text" placeholder="Фамилия" v-model="searchElementData.surname">
                    <input type="text" placeholder="Имя" v-model="searchElementData.name">
                    <input type="text" placeholder="Отчество" v-model="searchElementData.patronymic">
                    <input type="text" placeholder="Группа" v-model="searchElementData.group">
                    <input type="submit" value="Найти" @click.prevent="searchElement" @mouseup="deleteFocus">
                </form>
                <form id="delete-form" class="delete-form" @submit.prevent="deleteElement">
                    <input type="number" placeholder="id" v-model="delElementData.id">
                    <input type="text" placeholder="Фамилия" v-model="delElementData.surname">
                    <input type="text" placeholder="Имя" v-model="delElementData.name">
                    <input type="text" placeholder="Отчество" v-model="delElementData.patronymic">
                    <input type="text" placeholder="Группа" v-model="delElementData.group">
                    <input type="submit" value="Удалить" @click.prevent="deleteElement" @mouseup="deleteFocus">
                </form>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Control_buttons",
        data() {
            return {
                addElementData: {
                    id: null,
                    surname: "",
                    name: "",
                    patronymic: "",
                    group: ""
                },
                searchElementData: {
                    id: null,
                    surname: "",
                    name: "",
                    patronymic: "",
                    group: ""
                },
                delElementData: {
                    id: null,
                    surname: "",
                    name: "",
                    patronymic: "",
                    group: ""
                }
            }
        },
        methods: {
            addElement: function () {
                if (this.addElementData.id === null
                    && this.addElementData.surname === ""
                    && this.addElementData.name === ""
                    && this.addElementData.patronymic === ""
                    && this.addElementData.group === "") {
                    return
                }
                this.$emit('addElement', this.addElementData)
                this.addElementData.id = null
                this.addElementData.surname = this.addElementData.name = this.addElementData.patronymic
                    = this.addElementData.group = ""

            },
            searchElement: function () {
                if (this.searchElementData.id === null
                    && this.searchElementData.surname === ""
                    && this.searchElementData.name === ""
                    && this.searchElementData.patronymic === ""
                    && this.searchElementData.group === "") {
                    return
                }
                this.$emit('searchElement', this.searchElementData)
                this.searchElementData.id = null
                this.searchElementData.surname = this.searchElementData.name = this.searchElementData.patronymic
                    = this.searchElementData.group = ""
            },
            deleteElement: function () {
                if (this.delElementData.id === null
                    && this.delElementData.surname === ""
                    && this.delElementData.name === ""
                    && this.delElementData.patronymic === ""
                    && this.delElementData.group === "") {
                    return
                }
                this.$emit('delElement', this.delElementData)
                this.delElementData.id = null
                this.delElementData.surname = this.delElementData.name = this.delElementData.patronymic
                    = this.delElementData.group = ""
            },
            deleteFocus: function (e) {
                e.target.blur()
            }
        }
    }
</script>


<style scoped>
    .control-buttons-section {
        display: flex;
        justify-content: center;
        min-height: 20vh;
    }

    .forms-container {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }

    form {
        padding: 10px;
    }

    input {
        outline: none;
        border: 2px solid black;
        transition: 0.2s;
        margin-bottom: 5px;
    }

    input[type="text"]:hover, input[type="number"]:hover {
        border: 2px solid dimgrey;
    }

    input::-webkit-input-placeholder {
        text-align: center;
        color: black;
    }

    input[type="number"] {
        width: 58px;
        height: 30px;
        margin-right: 5px;
    }

    input[type="text"] {
        width: 200px;
        height: 30px;
        margin-right: 5px;
    }

    input[type="submit"] {
        width: 100px;
        height: 30px;
        background-color: white;
        font-weight: bold;
        cursor: pointer;
    }

    .insert-form input[type="text"]:focus, .insert-form input[type="number"]:focus {
        border: 2px solid limegreen;
    }

    .search-form input[type="text"]:focus, .search-form input[type="number"]:focus {
        border: 2px solid deepskyblue;
    }

    .delete-form input[type="text"]:focus, .delete-form input[type="number"]:focus {
        border: 2px solid red;
    }

    .insert-form input[type="submit"] {
        border: 2px solid limegreen;
        color: limegreen;
    }

    .insert-form input[type="submit"]:hover, .insert-form input[type="submit"]:focus {
        border: 2px solid limegreen;
        color: white;
        background-color: limegreen;
    }

    .search-form input[type="submit"] {
        border: 2px solid deepskyblue;
        color: deepskyblue;
    }

    .search-form input[type="submit"]:hover, .search-form input[type="submit"]:focus {
        border: 2px solid deepskyblue;
        color: white;
        background-color: deepskyblue;
    }

    .delete-form input[type="submit"] {
        border: 2px solid red;
        color: red;
    }

    .delete-form input[type="submit"]:hover, .delete-form input[type="submit"]:focus {
        border: 2px solid red;
        color: white;
        background-color: red;
    }

    @media (max-width: 1010px){
        .forms-container{
            flex-direction: row;
        }

        form{
            width: max-content;
            display: flex;
            flex-direction: column;
            justify-content: space-evenly;
        }
    }
    @media (max-width: 730px){
        .forms-container{
            align-items: center;
            flex-direction: column;
        }

        form{
            width: 80%;
            max-width: 300px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-evenly;
        }

        input[type="text"]{
            width: 100%;
        }

        input[type="number"]{
            width: 100%;
        }
    }

</style>