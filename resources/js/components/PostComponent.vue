<template>
    <div>
        <SinglePostComponent></SinglePostComponent>
        <div> Name: {{name}}</div>
        <button @click="sayHello"> Hello</button>
        <button @click="sayHi"> Hi</button>
    </div>
</template>

<script>
import SinglePostComponent from "@/components/SinglePostComponent.vue";
export default {
    name: "PostComponent",

    data() {
        return {
            name: 'Ivan',
            age: 18
        }
    },

    methods: {
        sayHello() {
            console.log('Hello')
        },
        sayHi() {
            console.log('Hi')
        },
    },
    components: {SinglePostComponent}
}
</script>

<style scoped>

</style>
