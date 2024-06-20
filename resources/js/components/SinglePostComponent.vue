<template>
    <div>
        <table class="table">
            <thead>
            <tr>
                <th scope="col">#</th>
                <th scope="col">Name</th>
                <th scope="col">Age</th>
                <th scope="col">Job</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="person in oldPerson">
                <th scope="row">{{ person.id }}</th>
                <td>{{ person.name }}</td>
                <td>{{ person.age }}</td>
                <td>{{ person.job }}</td>
            </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    name: "SinglePostComponent",

    data() {
        return {
            persons: [
                {
                    id: 1,
                    name: 'Vika',
                    age: 20,
                    job: 'lawyer',
                },
                {
                    id: 2,
                    name: 'Dima',
                    age: 25,
                    job: 'coach',
                },
                {
                    id: 3,
                    name: 'Sasha',
                    age: 29,
                    job: 'rest',
                },
            ]
        }
    },

    computed: {
        oldPerson() {
            return this.persons.filter(function(person) {
                return person.age > 22
            })
        }
    }
}
</script>

<style scoped>

</style>
