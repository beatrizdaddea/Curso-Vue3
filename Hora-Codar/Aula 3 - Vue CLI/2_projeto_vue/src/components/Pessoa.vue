<template>
    <div>
        <h2> Está é a descrição da pessoa: {{ nome }}</h2>
        <Info/>
        <Form/>
    </div>
</template>

<script>
import Info from './Info.vue'
import Form from './Form.vue'

    export default{
        name: "pessoa",
        components:{
            Info,
            Form,
        },
        data(){
            return{
                nome: "Beatriz"
            }
        }
    }
</script>
