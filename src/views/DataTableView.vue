<template>
    <div class="about">
      <data-table :headers="headers" :items="items" />
    </div>
  </template>
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
                    text: "Descrição"
                }
            ],
            items: []
        }
    },
})
</script>