<template>
    <div>
      <h1>Hello Vue!</h1>
      <p>Meu nome é {{ nome }} e sou uma {{ profissao }}</p>
      <MultiplosEventos/>
    </div>
  </template>

  <script>
  import MultiplosEventos from './MultiplosEventos.vue';
  export default {
    name: "PrimeiroComponente",
    components: {
      MultiplosEventos,
    },
    data() {
        return {
            nome: "Beatriz",
            profissao: "Programadora Back End"
        };
    },
    components: { MultiplosEventos }
}
  </script>