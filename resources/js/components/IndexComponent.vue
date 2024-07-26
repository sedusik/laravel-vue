<template>
    <div>
        <table class="table">
            <thead>
            <tr>
                <th scope="col">#</th>
                <th scope="col">Имя</th>
                <th scope="col">Возраст</th>
                <th scope="col">Должность</th>
                <th scope="col">Редактирование</th>
            </tr>
            </thead>
            <tbody>
            <template v-for="person in people" >
                <tr :class="isEdit(person.id) ? 'd-none' : ''">
                    <th scope="row">{{ person.id }}</th>
                    <td>{{ person.name }}</td>
                    <td>{{ person.age }}</td>
                    <td>{{ person.job }}</td>
                    <td><a href="#" @click.prevent="changeEditPersonId(person.id, person.name, person.age, person.job)" class="btn btn-success">Редактировать</a></td>
                </tr>
                <tr :class="isEdit(person.id) ? '' : 'd-none'">
                    <th scope="row">{{ person.id }}</th>
                    <td><input type="text" v-model="name" class="form-control"></td>
                    <td><input type="number" v-model="age" class="form-control"></td>
                    <td><input type="text" v-model="job" class="form-control"></td>
                    <td><a href="#" @click.prevent="updatePerson(person.id)" class="btn btn-dark">Обновить</a></td>
                </tr>
            </template>
            </tbody>
        </table>
    </div>
</template>
<script>
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

    methods: {
        getPeople() {
            axios.get('/api/people')
                .then( res => {
                    this.people = res.data
                })
        },

        changeEditPersonId(id, name, age, job) {
            this.editPersonId = id
            this.name = name
            this.age = age
            this.job = job
        },

        isEdit(id) {
            return this.editPersonId === id
        },

        updatePerson(id) {
            this.editPersonId = null
            axios.patch(`/api/people/${id}`, {name: this.name, age: this.age, job: this.job})
                .then( res => {
                    this.getPeople()
                })
        }
    }
}
</script>

<style scoped>

</style>
