<template>
    <div id="main-banner">
        <h1>Blaze Cars</h1>
    </div>
</template>

<script>
    export default {
        name: "Banner"
    }
</script>

<style scoped>
    #main-banner {
        height: 500px;
        background-image: url("../../public/imgs/image-banner.jpg");
        background-size: cover;
        background-position: 0;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    h1 {
        text-transform: uppercase; 
        color: white;
        padding: 20px 120px; 
        background-color: black;
    }
</style>