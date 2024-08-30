<template>
    <div>
        <div class="tabela">
            <table>
                <thead>
                    <tr>
                        <th v-for="(header, index) in headers" :key="index">
                            {{header[`text`]}} 
                        </th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(item, indexItem) in items" :key="indexItem">
                        <td v-for="(header) in headers" :key="header[`text`]" :class="{'text-right': header[`align`] === 'right', 'text-left': header[`align`] === 'left'}" >
                            <slot  :name="`item.${header[`value`]}`" :item="item" :index="indexItem"  >
                                {{ item[header[`value`]] }}
                            </slot>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>
<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
    name: "DataTable",
    props:{
        items: [] as any[] ,
        headers: [] as any[],
    },
    computed:{
    },
    
    data(){
        return {
            
        };
    },
    
    methods:{
        
        
    }
})
</script>
<style  scoped>
    table {
	border-collapse: collapse;
    font-family: Tahoma, Geneva, sans-serif;
    min-width: 350px !important;
}
table td {
	padding: 15px;
}
table thead th {
	background-color: #54585d;
	color: #ffffff;
	font-weight: bold;
	font-size: 13px;
	border: 1px solid #54585d;
    padding: 10px;
}
table tbody td {
	color: #636363;
	border: 1px solid #dddfe1;
}
table tbody tr {
	background-color: #f9fafb;
}
table tbody tr:nth-child(odd) {
	background-color: #ffffff;
}
</style>