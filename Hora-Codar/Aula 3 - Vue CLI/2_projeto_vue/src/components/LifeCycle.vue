<template>
    <div> 
        <h1>Meu nome é {{ nome }}</h1>
        <p> Sou desenvovedor {{ trabalho }} </p>
    </div>

  </template>

  <script>
  export default {
    name: 'LifeCycle',
    data() {
      return {
        nome: "Ainda não sei",
        trabalho: "Não sei"
      }
    },
    created() {
        setTimeout(() => {
            this.nome = "Matheus"
            this.trabalho = "Mobile"
        }, 1000);
    },

    mounted(){
        setTimeout(() => {
            this.nome = "Pedro"
            this.trabalho = "Front End"
        }, 2000);
    },
    methods:{
      lifeCycle(){
        console.log("Executou");
      }
    }

    }
  </script>