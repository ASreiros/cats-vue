<template>
    <div>
        <button @click="$emit('refresh')">Refresh</button>
    </div>
</template>
<script>
    export default {
        name:'Refresh',

        emits:['refresh']
    }

</script>
<style scoped>
    div{
        width: 100%;
        text-align: center;
    }

    button{
        padding: 10px 20px;
        border-radius: 15%;
        background-color: brown;
        color: aliceblue;
        font-size: 18px;
        cursor: pointer;

    }
</style>