<template lang="">
        <div class="card">
            <div class="button">
                <a href="#" @click="$emit('favoritar', id)"><img src="../assets/imgs/heart-svgrepo-com.svg" alt="favoritar" width="15"></a>
            </div>
            <div class="image">
                <img src="../assets/imgs/Lovepik_com-401706045-a-box-of-medicine (1).png" alt="" width="150">
            </div>
            <div class="info">
                <span>Nome: {{nome}}</span>
                <span>Laboratório: {{Laboratorio}}</span>
                <span>Preço: {{preco}}</span>
            </div>
        </div>   
</template>

<script>
export default {
    props: ["nome", "laboratorio", "preco", "favorito", "id"]
}
</script>

<style scoped>
.card {
    display: flex;
    flex-direction: column;
    width: calc(100%/5); 
    
    background-color: #c4c4c4c4;

}
.button{
    display: flex;
    justify-content:end;
    padding: 5px;
}
.image{
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #eaeaea;


}
.info{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 1rem;

}
</style>