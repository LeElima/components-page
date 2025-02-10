<template>
    <div class="curriculo">
        <div class="titulo colunaInicio">
            <h3>Leandro de Lima</h3>
        </div>
        <br />
        <div class="adress colunaInicio">
            <p>Rua Santa Terezinha 90 B</p>
            <p>Toledo-MG 37630-000</p>
            <p>(+55 11)95589-7339</p>
            <p>leandrolimaa2008@hotmail.com</p>
        </div>
        <br />
        <div class="skills colunaInicio">
            <p>javascript, html, css, c#, vuejs, SQL</p>
        </div>
        <br />
        <div class="educations colunaInicio">
            <div class="education">
                <h4>FATEC Antonio Russo - Bacharel</h4>
                <p>01-2014 to 06-2015</p>
            </div>
        </div>
        <br />
        <div class="experiences colunaInicio">
            <div class="experience colunaInicio">
                <h4>COBRAPE - Programador</h4>
                <p>01-2014 to 06-2015</p>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec ut semper massa. Vestibulum vulputate euismod nunc ac fermentum. Donec bibendum orci eu aliquam sagittis. In cursus mauris at faucibus aliquam. Curabitur gravida libero et sem tempus gravida. Praesent molestie ex non ipsum molestie accumsan. Suspendisse rhoncus ultricies magna, sed commodo magna blandit vel. Proin sed sapien est. Praesent efficitur vehicula elit, ut rutrum massa vestibulum lacinia. Quisque nec mi eu velit imperdiet interdum. Etiam non scelerisque nulla. Sed tristique interdum velit. Donec nulla nibh, ullamcorper sed ligula in, lobortis tempus nunc. Nam eu consequat est, in ullamcorper tortor. Phasellus sit amet augue aliquam, scelerisque elit non, varius mi. </p>
            </div>
        </div>
        <div class="others colunaInicio">
            <p>Inglês Avançado</p>
        </div>
    </div>
</template>
<style>
    .colunaInicio{
        display: flex;
        flex-direction: column;
        align-items: start;
    }
    .curriculo{
        background-color: antiquewhite;
        height: 100%;
        padding: 30px;
        width: 35em;
    }
    
    .adress p{
        color: black;
        line-height: 20px;
        font:  15px sans-serif;
    }

    .skills p{
        color: black;
        line-height: 20px;
        font:  15px sans-serif;
    }
    .education{
        display: flex;
        flex-direction: column;
        align-items: start;
    }
    .education h4{
        color: cadetblue;
        font: bold 16px sans-serif;
    }
    .education p{
        color: black;
        line-height: 20px;
        font:  12px sans-serif;
    }
    .experience h4{
        color: cadetblue;
        font: bold 16px sans-serif;
    }
    .experience p{
        color: black;
        line-height: 20px;
        font:  12px sans-serif;
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