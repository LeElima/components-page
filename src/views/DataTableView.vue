<template>
    <div class="about">
        <h1>DataTable</h1>
        <div class="tabela">
            <data-table :headers="headers" :items="items" />
        </div>
      
    </div>
  </template>
  <style>
    .about{
        display: flex;
    flex-direction: column;
    }
    .tabela{
        display: flex;
        justify-content: center;
        
    }
</style>
<script lang="ts">
import Vue from 'vue';
import DataTable from '@/components/DataTable.vue';
export default Vue.extend({
    components:{
        DataTable
    },
    data(){
        return{
            headers: [
                {
                    text: "Nome",
                    value: "nome"
                },
                {
                    text: "Idade",
                    value: "idade"
                },
                {
                    text: "Profissão",
                    value: "profissao"
                },
            ],
            items: [
                {
                    nome: "Leandro",
                    idade: "28",
                    profissao: "Programador"
                },
                {
                    nome: "João",
                    idade: "60",
                    profissao: "Aposentado"
                },
            ]
        }
    },
})
</script>