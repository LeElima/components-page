<template>
    <div class="pagina">
        <h1>Estudo CSS</h1>
        <h3>A idéia é pensar no css como caixas</h3>
        <div class="exemplo1">
            <div class="quadrado quadrado1">
                <h4>Texto</h4>
            </div>
        </div>
        
        <div class="exemplo3">
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
        <div class="exemplo4">
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
    </div>
    
  </template>
  <style>
  .quadrado{
    margin: 2px;
    width: 100px;
    height: 100px;
    background-color: orange;
  }
    div .exemplo1 .quadrado1{
    }
    div .exemplo1 .quadrado2{
        display: flex;
        align-items: start;

    }
    div .exemplo2 .quadrado3{
        display: flex;
        align-items: center;
    }
    div .exemplo2 .quadrado4{
        display: flex;
        align-items:end;
    }
    .exemplo3{
        display: flex;
        justify-content: space-evenly;
    }
    .exemplo4{
        display: flex;
        justify-content: space-evenly;
    }
    .quadrado5{
        display: flex;
        align-items:start;
    }
    .quadrado6{
        display: flex;
        align-items:center;
    }
    .quadrado7{
        display: flex;
        align-items:end;
    }
    .quadrado8{
        display: flex;
        justify-content: start;
    }
    .quadrado9{
        display: flex;
        justify-content: center;
    }
    .quadrado10{
        display: flex;
        justify-content: end;
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