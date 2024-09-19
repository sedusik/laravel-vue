<template>
    <div class="h3 mb-3 pt-4">
        Список сотрудников компании
    </div>
    <div>
        <table class="table">
            <thead>
            <tr>
                <th scope="col">ID</th>
                <th scope="col">Имя</th>
                <th scope="col">Возраст</th>
                <th scope="col">Должность</th>
                <th scope="col">Редактирование</th>
                <th scope="col">Удаление</th>
            </tr>
            </thead>
            <tbody>
            <template v-for="person in people" >
                <ShowComponent :person="person"></ShowComponent>
                <EditComponent :person="person" :ref="`edit_${person.id}`"></EditComponent>
            </template>
            </tbody>
        </table>
    </div>
</template>
<script>
import EditComponent from "./EditComponent.vue";
import ShowComponent from "./ShowComponent.vue";
import axios from "axios";

export default {
    name: "IndexComponent",

    data() {
        return {
            people: null,
            editPersonId: null,
            name: null,
            age: null,
            job: '',
        }
    },

    mounted() {
        this.getPeople()
    },

    components: {
        EditComponent,
        ShowComponent
    },

    methods: {
        getPeople() {
            axios.get('/api/people')
                .then( res => {
                    this.people = res.data
                })
        },

        isEdit(id) {
            return this.editPersonId === id
        },
    }
}
</script>

<style scoped>

</style>
