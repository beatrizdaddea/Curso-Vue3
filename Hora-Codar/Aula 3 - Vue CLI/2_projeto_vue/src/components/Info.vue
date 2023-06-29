<template>
    <div>
        <p v-if ="esta_trabalhando"> Estou trabalahndo no momento.</p>
        <p v-else> Estou buscando novas oportunidades.</p>
        <p> Utilizo as seguintes tecnologias: </p>
        <ul>
            <li> JavaScript</li>
            <li> PHP </li>
            <li> Python </li>
        </ul>
        <p v-show="mostrar_email"> Mande uma mensagem para: {{ email }}</p>
        <p> Para Acessar meu Portifólio <a v-bind:href = "meu_link">basta clicar aqui</a></p>
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
            }
        }
    }
</script>
