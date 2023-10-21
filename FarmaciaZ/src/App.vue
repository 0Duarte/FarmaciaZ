<template>
  <div id="container-super">
    <Header />
    <FormularioNovoMedicamento @cadastrar="AdicionarMedicamento" />
    <div class="container-cards">
      <CardMedicamento 
      v-if="!!listaMedicamentos"
      v-for="medicamento in listaMedicamentos"
      :key="medicamento.id"
      @favoritar="favoritarMed" 
      :nome="medicamento.nome" 
      :laboratorio="medicamento.laboratorio" 
      :preco="medicamento.preco" 
      :id="medicamento.id" 
    />
    </div>
  </div>
</template>


<script>
import { v4 as uuidv4 } from 'uuid';
import Header from "./components/Header.vue"
import FormularioNovoMedicamento from "./components/FormularioNovoMedicamento.vue"
import CardMedicamento from "./components/CardMedicamento.vue"


export default {
  data() {
    return {
      listaMedicamentos:[]
    }
  },
  components: {
    Header, FormularioNovoMedicamento, CardMedicamento
  },
  methods: {
    AdicionarMedicamento(nomeMed, nomeLab, preco) {
      if (nomeMed == "" || nomeLab == "" || preco == 0) {
        alert("Preencha todos os campos")
      } else {
        const novoMedicamento = {
          id: uuidv4(),
          nome: nomeMed,
          laboratorio: nomeLab,
          preco: preco,
          favorito: false
        }
        this.listaMedicamentos.push(novoMedicamento)
      }
    }
  }
}

</script>

<style scoped>
  #container-super{
    display: flex;
    margin-left: 20%;
    margin-right: 20%;
    flex-direction: column;
    gap: 1rem;
  }
  .container-cards{
    display: flex;
    max-width: 100%;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;

  }
</style>
