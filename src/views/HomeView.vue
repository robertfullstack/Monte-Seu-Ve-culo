<template>
  <div class="main-container">
    <div>
      <Banner />
    </div>

    <form action="">
    <h1>Monte do seu veículo:</h1>
      <Form />
    </form>
  </div>
</template>

<script>
import Banner from '@/components/Banner.vue';
import Form from '@/components/Form.vue';
export default {
  name: 'HomeView',
  components: {
    Banner,
    Form
  }
}
</script>

<style scoped>
  form {
    width: 400px;
    padding: 40px;
    margin: auto;
  }
</style>