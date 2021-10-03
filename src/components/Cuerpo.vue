<template>
  <div>
    <ul>
      <li v-for="(producto, x) in productos" :key="x">
        <h3>{{producto.description}} (cod: {{producto.id}} - ${{producto.precio}})</h3><button @click="modificar(x)">Modificar</button><input class="modif" type="hidden" placeholder="descripcion"/><input class="modif" type="hidden" placeholder="precio"/><button class="modif" hidden="hidden" @click="aceptar(x)">Aceptar</button><button @click="eliminar(x)">Eliminar</button>
      </li>
    </ul>
    <h3>Nuevo producto</h3>
    <input id="descripcion" type="text" placeholder="descripcion"/>
    <input id="precio" type="text" placeholder="precio"/>
    <button @click="agregar()">Agregar</button>
  </div>
</template>

<script>
  export default {
    name: 'Cuerpo',
    props: ['productos'],
    methods: {
      agregar: function (){
        this.productos.push({id: `${this.productos.length+1}`, description: `${document.getElementById('descripcion').value}`, precio: `${document.getElementById('precio').value}`})
      },
      eliminar: function (index){
        index = parseInt(index)
        document.getElementsByClassName('modif')[index*3+2].hidden="hidden"
        document.getElementsByClassName('modif')[index*3].type="hidden"
        document.getElementsByClassName('modif')[index*3+1].type="hidden"
        this.productos.splice(index, 1)
      },
      modificar: function (index){
        index = parseInt(index)
        document.getElementsByClassName('modif')[(index)*3].type="text"
        document.getElementsByClassName('modif')[(index)*3+1].type="text"
        document.getElementsByClassName('modif')[(index)*3+2].hidden=""
      },
      aceptar: function(index){
        index = parseInt(index)
        this.productos[index].description = document.getElementsByClassName('modif')[index*3].value
        this.productos[index].precio = document.getElementsByClassName('modif')[index*3+1].value
        document.getElementsByClassName('modif')[index*3].type="hidden"
        document.getElementsByClassName('modif')[index*3+1].type="hidden"
        document.getElementsByClassName('modif')[index*3+2].hidden="hidden"
      }
    }
  }
</script>