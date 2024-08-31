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
        <br />
        <div class="linha">
            <div class="quadrado_maior_wrap">
                
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
                    <div class="qd"></div>
            </div>
        </div>
        <h3>Aqui foi usado o flex-wrap, flex-direction,</h3>
        <h3>Pode usar o: flex-flow para juntar as duas propriedades</h3>
        <h3>Foi usado o align-content, que combinado com o flex-wrap define o alinhamento das linhas</h3>
        <h3>align-items nesse caso determina também como os items como um todo são alinhados no container</h3>
        <br />
        <div class="linha">
            <div class="quadrado_maior_teste">
                <div class="coluna esquerda">
                    <div>a</div>
                    <div>a</div>
                    <div>a</div>
                </div>
                <div class="coluna direita">
                    <div>b</div>
                    <div>b</div>
                    <div>b</div>
                </div>
            </div>
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
  .quadrado_maior_wrap{
    margin: 2px;
    width: 300px;
    height: 300px;
    background-color: orange;
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
    /*flex-flow: column wrap  */
    /* Pode usar tmb o align-content */
    align-content: space-around
  }
  .quadrado_maior_teste{
    margin: 2px;
    width: 300px;
    height: 300px;
    background-color: orange;
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;

  }
  .coluna{
    border: 1px dotted black;
    width: 50%;
    height: 100%;
  }
  .qd{
    width: 50px;
    height: 50px;
    border: 1px solid black;
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
    .especial{
        order: -1;
    }
    .especial2{
        align-self: end
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