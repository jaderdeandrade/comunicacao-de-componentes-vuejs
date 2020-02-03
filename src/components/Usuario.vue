<template>
  <div class="container">
    <h1>Componente Usuário</h1>
    <p>Esse é um componente muito legal!</p>
    <p>
      Nome é
      <strong>{{ nome }}</strong>
    </p>
    <button @click="alterarNome">Alterar Nome</button>
    <p>
      Idade :
      <strong>{{ idade }}</strong>
    </p>
    <hr />

    <div class="componentes">
      <app-usuario-info :nome="nome" :idade="idade" @nomeMudou="nome = $event" />

      <app-usuario-editar   :idade ="idade"  @idadeMudou="idade = $event + 1"/>
    </div>
  </div>
</template>

<script>
import AppUsuarioInfo from "./UsuarioInfo";
import AppUsuarioEditar from "./UsuarioEditar";

export default {
  components: { AppUsuarioInfo, AppUsuarioEditar },
  data() {
    return {
      nome: "Maria Lucia"
    };
  },
  methods: {
    alterarNome() {
      this.nome = "Maria Paula";
      this.idade = 21;
    }
  }
};
</script>

<style scoped>
.container {
  background-color: #27363b;
  color: #fff;
  padding: 10px;
}

.container hr {
  margin: 20px 10px;
}

.componentes {
  display: flex;
}

.componentes > * {
  margin: 10px;
}
</style>
