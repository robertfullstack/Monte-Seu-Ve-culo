<template>
    <div>
        <Messagem :msg="msg" v-show="msg"/>
        <div>
            <form action="" id="main-form" @submit="createCar">
                <div class="input-container">
                    <label for="name">Nome do Cliente</label>
                    <input type="text" name="nome" id="nome" v-model="nome" placeholder="Digite Seu Nome">
                </div>
                <div class="input-container">
                    <label for="modelo">Escolha o Estilo:</label>
                    <select name="modelo" id="modelo" v-model="modelos">
                        <option value="" selected disabled>Selecione o Estilo</option>
                        <option v-for="estilo in estilo" :key="estilo.id" :value="estilo.tipo">{{ estilo.tipo }}</option>
                    </select>
                </div>
                <div class="input-container">
                    <label for="forca">Escolha A Força:</label>
                    <select name="forca" id="forca" v-model="modelo">
                        <option value="" selected disabled>Selecione a Força</option>
                        <option v-for="forca in forca" :key="forca.id" :value="forca.tipo">{{ forca.tipo }}</option>
                    </select>
                </div>
                <div>
                    <button type="submit">Criar Meu Veículo</button>
                </div>
            </form>
        </div>
    </div>
</template>


<script>
import Messagem from './Messagem.vue';
    export default {
        name: "Form",
        data() {
            return {
                // listaModelosd: ["Acura", "Alfa Romeo"],
                nome: null,
                estilo: null,
                forca: null
                // listaForca: ["Muita", "Média", "Pouca"],
                // status: "Solicitado"
            }
        },
        components: {
            Messagem
        },
        methods: {
            async getModelos() {
                const req = await fetch("http://localhost:3000/modelos")
                const data = await req.json();

                this.estilo = data.estilo;
                this.forca = data.forca;
            },

            async createCar(e) {
                e.preventDefault();

                const data = {
                    nome: this.nome,
                    estilo: this.estilo,
                    forca: this.forca,
                    status: "Solicitado"
                }

                const datajson = JSON.stringify(data)

                const req = await fetch("http://localhost:3000/desejo", {
                    method: "POST",
                    headers: { "Content-Type" : "application/json" },
                    body: datajson
                });

                const res = await req.json()

                // msg do sistema
                this.msg = `Pedido Nº ${res.id} Enviado Com Sucesso!`

                // limpar msg
                setTimeout(() => {
                    this.msg = ""
                }, 4000);
                // setTimeout(()=> this.msg = "", 4000)
                // limpar os campos
                this.nome = "";
                this.estilo = "";
                this.forca = "";

                console.log(res)
            }
        },
        mounted() {
            this.getModelos()
        }
    }
</script>

<style scoped>
    .input-container{
        margin: 20px 10px;
    }
    .input-container label {
        border-left: 4px solid #00ff84;
        margin: 15px;
        padding: 4px 10px;
    }
    label {
        display: block;
    }
    input, select {
        display: block;
        padding: 3px 10px;
        width: 80%;
        margin: auto;   
    }
</style>