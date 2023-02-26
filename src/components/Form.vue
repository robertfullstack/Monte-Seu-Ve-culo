<template>
    <div>
        <p>Componente de Mensagem</p>
        <div>
            <form action="" id="main-form">
                <div class="input-container">
                    <label for="name">Nome do Cliente</label>
                    <input type="text" name="name" id="name" v-model="name" placeholder="Digite Seu Nome">
                </div>
                <div class="input-container">
                    <label for="modelo">Escolha o Estilo:</label>
                    <select name="modelo" id="modelo" v-model="modelo">
                        <option value="" selected disabled>Selecione o Estilo</option>
                        <option value="" v-for="(modelos, index) in listaModelos" :key="index">{{ modelos }}</option>
                    </select>
                </div>
                <div class="input-container">
                    <label for="forca">Escolha A Força:</label>
                    <select name="forca" id="forca" v-model="modelo">
                        <option value="" selected disabled>Selecione a Força</option>
                        <option value="" v-for="(forca, index) in listaFoca" :key="index">{{ forca }}</option>
                    </select>
                </div>
            </form>
        </div>
    </div>
</template>


<script>
    export default {
        name: "Form",
        data() {
            return {
                listaModelosd: ["Acura", "Alfa Romeo"],
                listaModelos: ["Alto", "Baixo", "Medio","Rebaixado"],
                listaFoca: ["Muita", "Média", "Pouca"]
            }
        }
    }
</script>

<style scoped>

</style>