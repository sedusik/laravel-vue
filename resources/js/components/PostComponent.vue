<template>
    <div>
<!--        <SinglePostComponent></SinglePostComponent>-->
        <CreateComponent></CreateComponent>
        <IndexComponent></IndexComponent>
<!--        <div> Name: {{name}}</div>-->
<!--        <div>Job: {{ivanJob}}</div>-->
<!--        <button @click="sayHello"> Hello</button>-->
<!--        <button @click="sayHi"> Hi</button>-->
    </div>
</template>

<script>
import SinglePostComponent from "./SinglePostComponent.vue";
import CreateComponent from "./CreateComponent.vue";
import IndexComponent from "./IndexComponent.vue";
export default {
    name: "PostComponent",

    data() {
        return {
        //     name: 'Ivan',
        //     age: 18
        }
    },

    mounted() {

    },

    methods: {
        // sayHello() {
        //     console.log('Hello')
        // },
        // sayHi() {
        //     console.log('Hi')
        // },
    },

    computed: {
        // ivanJob() {
        //     return this.name + ' работает дизайнером'
        // }
    },
    components: {
        CreateComponent,
        SinglePostComponent,
        IndexComponent
    }
}
</script>

<style scoped>

</style>
