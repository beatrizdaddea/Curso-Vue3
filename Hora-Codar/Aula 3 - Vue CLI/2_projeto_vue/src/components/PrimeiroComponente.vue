<template>
    <div>
      <h1>Hello Vue!</h1>
      <p>Meu nome é {{ nome }} e sou uma {{ profissao }}</p>
    </div>
  </template>

  <script>
  export default {
    name: 'PrimeiroComponente',
    data() {
      return {
        nome: "Beatriz",
        profissao: "Programadora Back End"
      }
    }
  }
  </script>