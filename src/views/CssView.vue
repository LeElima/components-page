<template>
    <div class="pagina">
        <h1>Estudo CSS</h1>
        <h3>A idéia é pensar no css como caixas</h3>
        <div class="exemplo1">
            <div class="quadrado quadrado1">
                <h4>Texto</h4>
            </div>
        </div>
        
        <div class="linha">
            <div class="quadrado quadrado5">
                <h4>Texto</h4>
            </div>
            <div class="quadrado quadrado6">
                <h4>Texto</h4>
            </div>
            <div class="quadrado quadrado7">
                <h4>Texto</h4>
            </div>
        </div>
        <div class="linha">
            <div class="quadrado quadrado8">
                <h4>Texto</h4>
            </div>
            <div class="quadrado quadrado9">
                <h4>Texto</h4>
            </div>
            <div class="quadrado quadrado10">
                <h4>Texto</h4>
            </div>
        </div>
        <div class="linha">
            <div class="quadrado quadrado11">
                <h4>Texto</h4>
            </div>
            <div class="quadrado quadrado12">
                <h4>Texto</h4>
            </div>
            <div class="quadrado quadrado13">
                <h4>Texto</h4>
            </div>
        </div>
        <div >
            <h3>Foi usado o 'align-items' para alinhar no eixo x(vertical)</h3>
            <h3>Foi usado o 'justify-content' para alinhar no eixo y(horizontal)</h3>
        </div>
        <br />
        <div class="linha">
            <div class="quadrado_maior">
                <div class="topo">
                    <div class="borda">oi</div>
                    <div class="borda">oi</div>
                    <div class="borda">oi</div>
                </div>
                <div class="meio">
                    <div class="borda">oi</div>
                    <div class="borda">oioi</div>
                    <div class="borda">oii</div>
                </div>
                <div class="baixo">
                    <div class="borda">oio</div>
                    <div class="borda">oiio</div>
                    <div class="borda">oiioi</div>
                </div>
            </div>
        </div>
        <div >
            <h3>Foi usado o 'flex-direction' para alinhar a direção dos items</h3>
            
        </div>
    </div>
    
  </template>
  <style>
  .quadrado{
    margin: 2px;
    width: 100px;
    height: 100px;
    background-color: orange;
  }
  .quadrado_maior{
    margin: 2px;
    width: 300px;
    height: 300px;
    background-color: orange;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
    
     
    .linha{
        display: flex;
        justify-content: space-evenly;
    }
    .quadrado5{
        display: flex;
        align-items:start;
    }
    .quadrado6{
        display: flex;
        justify-content: center;
    }
    .quadrado7{
        display: flex;
        justify-content: end;
    }
    .quadrado8{
        display: flex;
        align-items:center;
    }
    .quadrado9{
        display: flex;
        justify-content: center;
        align-items:center;
    }
    .quadrado10{
        display: flex;
        align-items:center;
        justify-content: end;
    }
    .quadrado11{
        display: flex;
        justify-content: start;
        align-items: end;
    }
    .quadrado12{
        display: flex;
        justify-content: center;
        align-items: end;
    }
    .quadrado13{
        display: flex;
        justify-content: end;
        align-items: end;
    }
    .borda{
        border: 1px solid black;
    }
    .quadrado_maior .topo{
        display: flex;
        justify-content: space-around;
    }
    .quadrado_maior .meio{
        display: flex;
        justify-content: space-evenly;
        flex-direction: column;
    }
    .quadrado_maior .baixo{
        display: flex;
        justify-content: space-evenly;
        flex-direction: row-reverse;
    }
</style>
<script lang="ts">
import Vue from 'vue';
export default Vue.extend({
    data(){
        return{
            
        }
    },
})
</script>