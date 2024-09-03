<template >
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
                    <tr v-for="(item, indexItem) in treeData" :key="indexItem">
                        <td v-for="(header) in headers" :key="header[`text`]" :class="{'text-right': header[`align`] === 'right', 'text-left': header[`align`] === 'left'}" >
                          <slot v-if="header.value == 'icone'" :name="`item.icone`" :item="item" :index="indexItem" >
                            <td class="d-flex" style="float: right;">
                              <div>
                                <button @click="expandirRecolher(item, indexItem)">oi</button>
                              </div>
                            </td>
                          </slot>  
                          <slot v-else  :name="`item.${header[`value`]}`" :item="item" :index="indexItem"  >
                                {{ item[header[`value`]] }}
                            </slot>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
        
  </div>
    
    </template>
    
    <script>
    import Vue from 'vue';
    import DataTable from '@/components/DataTable.vue'
    export default Vue.extend({
      name:"DataTreeView",
      components:{
        DataTable
      },
      props: {
        treeData: {
          type: Array,
          required: true
        },
        headers:{
          type: Array,
        },
        impar: {
          type: Boolean,
          default: false
        },
        carregarHeader: {
          type: Boolean,
          default: true
        },
        nivel:{
          type: Number,
          default: 1
        }
      },
      computed:{
        classe(){
          return !this.impar
        },
        listaAtualizada(){
          
        }
      },
      mounted(){
        if(this.edicao || this.exclusao){
          if(this.headers.length == 0) return;
          if(this.headers[this.headers.length - 1].value == 'action')return;
          this.headers.push()({text: "", value: "action"})
        }
        this.headers.unshift({text: "", value: "icone"})
      },
      created(){
      },
      methods:{
        setPadding(value) {
          return `padding-left: ${value * 10}px;`;
          },
          expandirRecolher(item, index){
                item.expandido = !item.expandido;
                var itemsAntesDoClicado = this.treeData.slice(0,index+1);
                var itemsDepoisDoClicado = this.treeData.slice(index+1);
                var filhos = item.filhos;
                var itemsAtualizados = [...itemsAntesDoClicado, ...filhos, ...itemsDepoisDoClicado];
                    this.treeData = itemsAtualizados
                // if(item.expandido == true){
                //     var itemsAtualizados = [...itemsAntesDoClicado, ...filhos, ...itemsDepoisDoClicado];
                //     this.listaAreas = itemsAtualizados
                // }
                // else{
                //     var removerFilhos = (filhos, pai) => {
                //         if (pai.nivel === 1) { 
                //             return filtraBairros(filhos, pai)
                //         } else  { 
                //             return filtraLogradouros(filhos, pai)
                //         }
                //     };

                //     var filtraBairros = (items, area) => {
                        
                //         var bairros = items.filter(item => item.nivel === 2 && item.idArea === area.idArea);
                //         var restantes = items.filter(item => item.nivel !== 2 || item.idArea !== area.idArea);
                        
                //         bairros.forEach(bairro => {
                //             bairro.expandido = false;
                //             restantes = filtraLogradouros(restantes, bairro);
                //         });

                //         return restantes;
                //     };

                //     var filtraLogradouros = (items, bairro) => {
                //         var restantes = items.filter(item => item.nivel !== 3 || item.idBairro !== bairro.idBairro);
                //         return restantes;
                //     };
                //     var depoisSemFilho = removerFilhos(itemsDepoisDoClicado, item);
                //     var itemsAtualizados = [...itemsAntesDoClicado, ...depoisSemFilho];
                //     this.listaAreas = itemsAtualizados;
                // }
            },
      }
    });
    </script>
    
    <style scoped>
    .thead {
        background-color: #f2f2f2;
        font-weight: bold;
      }
    
  .body {
        margin: 0;
        padding: 0;
      }
    .row {
    display: flex;
    align-items: flex-start;
    border-bottom: 1px solid #ddd;
  }
  .cell {
        flex: 1;
        padding: 12px;
        box-sizing: border-box;
        
      }
  
      /* Remove border-right on the last cell of each row */
      .first, .other:last-child {
        border-right: none;
      }
  .first, .other {
    flex: 1;
        padding: 12px;
        box-sizing: border-box;
        border-right: 2px solid #ddd;
  }
  .row:nth-child(even) {
        background-color: #f9f9f9;
      }
  /* .first {
    flex-grow: 1;
  }
  
  .other {
    flex-basis: auto;
    flex-shrink: 1;
  } */
    </style>