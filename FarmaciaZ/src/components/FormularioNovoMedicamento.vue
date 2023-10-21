<template>
    <div class="container-cadastro">
        <div class="titulo">
            <h2>Formulário de cadastro de medicamentos</h2>
        </div>  
        <div class="cadastro-form">
            <label for="nome">Nome</label>
            <input type="text" id="nome" placeholder="Nome do medicamento" v-model="nome">

            <label for="laboratorio">Laboratório</label>
            <input type="text" id="laboratorio" placeholder="Nome do laboratório" v-model="laboratorio">

            <label for="preco">Preço</label>
            <input type="number" id="preco" placeholder="Preço" v-model="preco">

            <button @click="$emit('cadastrar', nome, laboratorio, preco)">Cadastrar</button>
        </div>

    </div>
</template>

<script>
    export default{
        data(){
            return{
                nome: "",
                laboratorio:"",
                preco: 0
            }
        }
    }
</script>

<style scoped>
    .container-cadastro{

        flex-direction: column;
        display: flex;
        gap: 15px;
        justify-content: space-around;
        align-items: start;
    }
    .cadastro-form{
        display: flex;
        align-items: space-between;
        width: 100%;
        gap: 5px;
    }
</style>