<template>
<ul  v-for="fact in facts">
    <Fact :fact="fact"></Fact>
</ul>
</template>
<script>
import Fact from './Fact.vue';
    export default{
    name: "Facts",
    props: {
        facts: Array,
    },
    components: { Fact }
}

</script>
<style scoped>
    ul{
        margin: 20px auto;
        width: 50vw;
        font-size: 24px;
    }
</style>