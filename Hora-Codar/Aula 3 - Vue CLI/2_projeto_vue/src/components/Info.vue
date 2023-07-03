<template>
    <div>
        <p v-if ="esta_trabalhando"> Estou trabalahndo no momento.</p>
        <p v-else> Estou buscando novas oportunidades.</p>
        <p> Utilizo as seguintes tecnologias para back-end: </p>
        <ul>
            <li  v-for="(technology, index) in backend_tecnologies" v-bind:key="index"> {{ technology }}</li>
        </ul>
        <p> Utilizo as seguintes tecnologias para front-end: </p>
        <ul>
            <li  v-for="technology in frontend_tecnologies" :key="technology.id"> {{ technology.language }}</li>
        </ul>
        <div>
            <button @click="showEmail"> {{ textoBotao }}</button>
        </div>
        <p v-show="mostrar_email"> Mande uma mensagem para: {{ email }}</p>
        <p class = "teste"> Para Acessar meu Portifólio <a v-bind:href = "meu_link">basta clicar aqui</a></p>
        <Picture />
    </div>
</template>

<script>
import Picture from './Picture'
  export default{
        name: "Info",
        components: {
            Picture,
        },
        data(){
            return{
                esta_trabalhando: false,
                mostrar_email: true,
                email: 'email@mail.com',
                meu_link: 'https://google.com',
                textoBotao: 'Mostrar Email',
                backend_tecnologies:["JavaScript", "PHP", "Phyton"],
                frontend_tecnologies:[
                    {id: 1, language: 'HTML'},
                    {id: 2, language: 'React'},
                    {id: 3, language: 'VUE3'},
                ]
            }
        },
        methods:{
            showEmail(){
                this.mostrar_email = !this.mostrar_email
                if(!this.mostrar_email){
                    this.textoBotao = 'Mostrar E-mail'
                } else{
                    this.textoBotao = 'Esconder E-mail'
                }
            }
        }
    }
</script>
