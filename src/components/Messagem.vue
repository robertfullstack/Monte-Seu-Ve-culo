<template>
    <div class="messagem-container">
        <p>{{ msg }}</p>
    </div>
</template>

<script>
    export default {
        name: 'Messagem',
        props: {
            msg: String
        }
    }
</script>

<style scoped>
    .messagem-container {
        color: #0040b5;
        background-color: #CCE5FF;
        border: 2px solid #D8DAFF;
        border-radius: 5px;
        padding: 10px;
        max-width: 400px;
        margin: 30px auto;
    }
</style>