<template>
    <div>
        <div>
            <table>
                <thead>
                    <tr>
                        <th v-for="(header, index) in headersL" :key="index">
                            {{header.name}}
                        </th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-if="itemsL.length == 0">
                        <td :colspan="headersL.length">Não há dados disponíveis</td>
                    </tr>
                    <tr v-else v-for="(item, index) in itemsTree" :key="index">
                        <td  v-for="(header, indexC) in headersL" :key="indexC" :data-th="header.nome" @click="expand(item, index)">
                            <slot :name="`item.${header.value}`" :item="item">
                                <span v-bind:style="setPadding(item)">
                                    {{item[`${header.value}`]}}
                                </span>
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
    name: "SmartList",
    props:{
        items: Array,
        headers: Array,
        sons: String,
        id: String
    },
    computed:{
        itemsTree(){
            var newObj:any=[];
                this.montarLinhas(this.itemsL, newObj, 0, this.itemId, this.isExpanded)
            return newObj;
        },
    },
    watch: {
        // itemsL:{
        //     immediate: true,
        //     handler(value){
        //         this.$emit("input", value);
        //     }
        // },
        // items: {
        //     immediate: true,
        //     handler(value){
        //         this.itemsL = value;
        //     }
        // }
    },
    data(){
        return {
            headersL: this.headers,
            itemsL: this.items,
            sonsL: this.sons,
            isExpanded: false,
            selectedRowID: {},
            itemId: this.id,
            key: this.id
        };
    },
    beforeMount(){
        if(this.itemsL && this.itemsL.length > 0){
            this.montarItems(this.itemsL, 0)
        }
    },
    methods:{
        montarItems(items: any, nivel: Number){
            if(items != undefined){
                items.forEach((x:any)=>{
                    x.nivel=nivel;
                    x.expansivel = true;
                    if(x[`${this.sonsL}`]){
                        var newNivel = Number(nivel) + 1;
                        this.montarItems(x[`${this.sonsL}`], newNivel)
                    }
                })
            }   
            
            
        },
        expand(item: any, index: number){
            if(item.expansivel == false && item[`${this.sonsL}`] != undefined){
                if(item[`${this.sonsL}`].length != 0){
                    // this.montarLinhas(item[`${this.sonsL}`], [], item.nivel +1, item.id, true)
                    this.isExpanded = true;
                    this.montarLinhas(item[`${this.sonsL}`], [], Number(item.nivel) +1, item[`${this.key}`], this.isExpanded)
                }
            }
            if(item.expansivel == true && item[`${this.sonsL}`] != undefined){
                this.isExpanded = false;
                item[`${this.sonsL}`].forEach((x:any)=>{
                    x.expansivel = this.isExpanded
                })
                item.expansivel = this.isExpanded;
                this.$set(item, "expansivel", this.isExpanded);
                //this.$set(item, "leaf", false);
                this.itemId = '';
            }
        },
        setPadding(item: any) {
            return `padding-left: ${item.nivel * 30}px;`;
        },
        montarLinhas(arrayObjetos: any, novoObjeto: any, nivel: any, idItem: any, expansivel: any){
            arrayObjetos.forEach((item:any) => {
                if(item[`${this.sonsL}`] && item[`${this.sonsL}`].length != 0){
                    item.nivel = nivel
                    novoObjeto.push(item)
                    console.log(item[`${this.key}`])
                    console.log(idItem)
                    if(item[`${this.key}`] == idItem){
                        item.expansivel = expansivel
                    }
                    if(item.expansivel == true){
                        
                        this.montarLinhas(item[`${this.sonsL}`], novoObjeto, item.nivel + 1, idItem, expansivel)
                    }
                }
                else{
                    item.nivel = nivel
                    novoObjeto.push(item)
                    return false;
                }
            })
        },
    }
})
</script>
<style  scoped>
    table{
        font-family:sans-serif;
        width:100%;
	    border:1px solid
        
    }
    td {
        text-align:left;
        background-color:#eee;    
    }
    th {
        padding:.25em .5em;
        background-color:#009;
        color:#fff;
    }
</style>