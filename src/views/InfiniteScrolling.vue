<template>
    <div ref="infiniteScroll">
        <div v-for="(item, index) in listaFotos" :key="index">
            <img :src="item.download_url" :alt="'Imagem ' + index" width="200" />
        </div>
    </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
    data(){
        return{
            listaFotos: [] as Array<{ download_url: string }>,
            pagina: 1,
        };
    },
    mounted() {
        window.addEventListener("scroll", this.rolarPagina);
    },
    beforeDestroy() { 
        window.removeEventListener("scroll", this.rolarPagina);
    },
    created(){
        this.carregarImagens()
    },
    methods: {
        async carregarImagens() {
            try {
                const myRequest = new Request("https://picsum.photos/v2/list?page="+this.pagina+"&limit=5");
                const response = await fetch(myRequest);

                if (!response.ok) {
                    throw new Error("Ops! Houve um erro em nosso servidor.");
                }

                const data = await response.json();
                this.listaFotos.push(...data);
                this.pagina ++;
            } catch (error) {
                console.error(error);
            }
        },

        rolarPagina() {
            const element = this.$refs.infiniteScroll as HTMLElement; 
            if (!element) return; 

            if (element.getBoundingClientRect().bottom < window.innerHeight) {
                this.carregarImagens();
            }
        }
    }
});
</script>
