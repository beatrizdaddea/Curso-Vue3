<template>
  <header>
    <h1>
      <img alt="Alura Tracker" src="../assets/logo.png">
    </h1>
    <div class="has-text-centered">
      <button class="button" @click="alterarModo">Ativar modo {{ textoBtn }}</button>
    </div>
    <nav class="panel mt-5">
      <ul>
        <li>
          <router-link to="/" class="link">
            <i class="fas fa-tasks"></i>
            Tarefas
          </router-link>
        </li>
        <li>
          <router-link to="/projetos" class="link">
            <i class="fas fa-project-diagram"></i>
            Projetos
          </router-link>
        </li>
        <li>
          <ToDoList/>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ToDoList from './ToDoList.vue';

export default defineComponent({
  name: "BarraLateral",
  emits: ['aoAlterarModo'],
  components: {
      ToDoList,
  },
  data () {
    return {
      modoEscuro: false
    }
  },
  methods: {
    alterarModo () : void {
      this.modoEscuro = !this.modoEscuro
      this.$emit('aoAlterarModo', this.modoEscuro)
    }
  },
  computed: {
    textoBtn () : string {
      return this.modoEscuro ? 'claro' : 'escuro'
    }
  }
});
</script>
<style scoped>
h1 {
  text-align: center;
}
strong {
  color: #f95738;
}
header {
  background: #ffc8e0;
  width: 100%;
  height: 100vh;
  padding: 2rem;
}
@media only screen and (max-width: 768px) {
  header {
    height: auto;
  }
}
.panel li {
  margin: 8px 0;
}
.link {
  color: #000000;
}
.link:hover {
  color: #7c7c7c;
}
.link.router-link-active {
  color: #000000;
}
</style>