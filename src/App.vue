<template>
  <div id="app">
    <cabecera v-bind:titulo="titulo"/>
    <cuerpo v-bind:productos="productos"/>
    <pie v-bind:autor="autor"/>
  </div>
</template>

<script>
  import Cabecera from '@/components/Cabecera.vue'
  import Cuerpo from '@/components/Cuerpo.vue'
  import Pie from '@/components/Pie.vue'
  export default {
    name: 'app',
    components: {
      Cabecera, Cuerpo, Pie
    },
    data (){
      return {
        titulo: 'NT2-TP5',
        autor: 'Jorge',
        productos: [
          {id: '1', description: 'Auriculares', precio: '100'},
          {id: '2', description: 'Microfono', precio: '200'},
          {id: '3', description: 'Parlante', precio: '300'}
        ]
      }
    }
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
