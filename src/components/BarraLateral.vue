<template>
    <header>
        <h1>
            <img src="../assets/Logo.png" alt="">
        </h1>
        <button class="Button" @click="alterarTema">
            {{ textoBotao }}
        </button>
    </header>
</template>

<script lang="ts">
    import {defineComponent} from 'vue'

    export default defineComponent 
    ({
        name:'BarraLateral',
        emits: ['aoTemaAlterado'],
        data () {
          return {
            modoEscuroAtivo: false
          }
        },
        computed: {
          textoBotao () {
            if (this.modoEscuroAtivo) {
              return 'Light'
            }
            return 'Dark'
          }
        },
        methods: {
          alterarTema () {
            this.modoEscuroAtivo = !this.modoEscuroAtivo
            this.$emit('aoTemaAlterado', this.modoEscuroAtivo)
          }
        }
    });
</script>

<style scoped>
  header {
  padding: 0.5rem;
  background: rgb(242,135,182);
  background: radial-gradient(circle, rgba(242,135,182,1) 0%, rgba(148,187,233,1) 100%);
  width: 100%;
  height: 100vh;
  text-align: center;
  }
  @media only screen and (max-width: 768px) {
    header {
      padding: 5.5rem;
      height: auto;
    }
  }

  Button{
    width: 70px;
    height: 45px;
    border-radius: 80px;
    text-shadow: none;
    opacity: 80%;
    border: 1px solid #f1d6f8;
    cursor:pointer;
  }
  Button:hover{
    background: linear-gradient(90deg, rgba(83, 14, 110, 0.726) 30%, rgba(252, 181, 246, 0.815) 100%);
    border: 1px solid #f1d6f8;
    color: #fff;
  }
</style>