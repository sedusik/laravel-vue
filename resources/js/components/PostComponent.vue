<template>
    <div>
        <CreateComponent></CreateComponent>
        <IndexComponent ref="index"></IndexComponent>
        <SinglePostComponent :obj="obj"></SinglePostComponent>
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
            obj: {
                color: 'red',
                number: 33,
                isPublished: true,
            }
        }
    },

    mounted() {
        console.log(this.$refs.index);
    },

    methods: {
        parentLog() {
            console.log('this is post component');
        }
    },

    computed: {

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
