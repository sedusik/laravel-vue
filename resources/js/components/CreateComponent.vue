<template>
    <div class="w-25">
        <div class="mb-3">
            <input type="text" class="form-control" v-model="name" id="name" placeholder="name">
        </div>
        <div class="mb-3">
            <input type="text" class="form-control" v-model="age" id="age" placeholder="age">
        </div>
        <div class="mb-3">
            <input type="text" class="form-control" v-model="job" id="job" placeholder="job">
        </div>
        <div class="mb-3">
            <input type="submit" @click.prevent="addPerson" class="btn btn-primary" value="Добавить">
        </div>
    </div>
</template>

<script>
import axios from "axios";

export default {
    name: "CreateComponent",

    data() {
        return {
            name: null,
            age: null,
            job: null,
        }
    },

    mounted() {
        this.$parent.$refs.index.indexLog()
    },

    methods: {
        addPerson() {
            axios.post('/api/people', {name: this.name, age: this.age, job: this.job})
                .then( res => {
                    this.name = null
                    this.age = null
                    this.job = null
                    this.$parent.$refs.index.getPeople()
                })
        }
    }
}
</script>

<style scoped>

</style>
