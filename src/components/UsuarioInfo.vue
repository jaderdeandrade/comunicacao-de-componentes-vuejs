<template>
    <div class="componente">
        <h2>As Informações de Usuário</h2>
        <p>Vários detalhes...</p>
        <p>Nome do usuário: <strong>{{ nome }}</strong></p>
        <p>Idade do usuário <strong>{{idade}}</strong></p>
     <button @click="reiniciarNome">Reiniciar nome</button> 
    </div>
</template>

<script>
export default {
    props: {
        nome: {
            type : String , 
            //required : true
            default: 'Anônimo'
        },
        idade : Number

    },
    methods: {
        reiniciarNome(){
           // this.nome  = 'Maria Lucia'
            

            this.$emit('nomeMudou', 'Maria Lucia')
        }

    }
}
</script>

<style scoped>
    .componente {
        flex: 1;
        background-color: #ec485f;
        color: #fff;
    }
</style>
