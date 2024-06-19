<template>
    <div>
        <SinglePostComponent></SinglePostComponent>
        <div> Name: {{name}}</div>
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
    components: {SinglePostComponent}
}
</script>

<style scoped>

</style>
