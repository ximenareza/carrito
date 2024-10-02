<script setup>
import { ref } from 'vue';
// Modelo
const header = ref('App lista de compras');
 // ----- Items
 //------- Item-Model
const items = ref([
  {id:'0', label: '10 bolillos'},
  {id:'1', label: '1 crema de litro'},
  {id:'2', label: '1/4 de jamon'},
  {id:'3', label: '1 nutella'}
]);
// Item-Method
const saveItem = () => {
  items.value.push({id: items.value.length + 1, label: newItem.value});
  // Limpia el input (Caja de texto)
  newItem.value = '';

};

const newItem = ref("");
const newItemHighPriority = ref(false);

</script>
 
<template>
  <h1>
   <i class="material-icons shopping-cart-icon">local_mall</i>
    {{ header }}
  </h1>
  <form v-on:submit.prevent="saveItem()">
  <input v-model="newItem" type="text" placeholder="Agregar un articulo" />
  <!--Caja de seleccion de Prioridad-->
  <label>
    <input type="checkbox" v-model="newItemHighPriority" />
    Alta Prioridad
  </label>
  <!--Boton-->
  <button class="btn btn-primary">
    Salvar Articulo
  </button>
  </form>
  <ul></ul>
  
  <!-- Lista -->
  <ul>
    <li v-for="item in items" :key="item.id"> 📌 {{  item.label }} </li>
  </ul>
</template>
 
<style scoped>
.shopping-cart-icon{
  font-size: 2rem;
}
</style>