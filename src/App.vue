<script setup>
import { ref } from 'vue';
// Modelo
const header = ref('App lista de compras');
 // ----- Items
 //------- Item-Model
const items = ref([
  {id:'0', label: '10 bolillos', purchased: false, priority: false},
  {id:'1', label: '1 crema de litro', purchased: true, priority: true},
  {id:'2', label: '1/4 de jamon', purchased: false, priority: false},
  {id:'3', label: '1 nutella', purchased: true, priority: true},
]);
// Item-Method
const saveItem = () => {
  items.value.push({id: items.value.length + 1, label: newItem.value});
  // Limpia el input (Caja de texto)
  newItem.value = '';

};

const newItem = ref("");
const newItemHighPriority = ref(false);
const editing = ref(true);
const activateEdition = (activate) => {
  editing.value = activate;
}

</script>
 
<template>
  <div class="header">
  <h1>
   <i class="material-icons shopping-cart-icon">local_mall</i>
    {{ header }}
  </h1>

<button v-if="editing" class="btn" @click="activateEdition(false)"> Cancelar</button>
<button v-else class="btn btn-primary" @click="activateEdition(true)">Agregar Articulo</button>
</div>




<form
class="add-item form"
   v-if="editing"
   v-on:submit.prevent="saveItem()">

  <input v-model="newItem" type="text" placeholder="Agregar un articulo" />
  <!--Caja de seleccion de Prioridad-->
  <label>
    <input type="checkbox" v-model="newItemHighPriority" />
    Alta Prioridad
  </label>
  <!--Boton-->
  <button 
  :disabled="newItem.length === 0"
  class="btn btn-primary">
    Salvar Articulo
  </button>
  
  </form>
  <ul></ul>
  
  <!-- Lista -->
  <ul>
    <li 
    v-for="{label, id, purchased, priority} in items" 
    :key="id"
    class="amazing"
    :class="{strikeout: purchased, priority: priority}"> 
    {{priority ? "🔥"  : "🛒"}} {{ label }}
    </li>
  </ul>
  <p v-if="items.length === 0">🥀 NO HAY ELEMENTOS EN LA LISTA 🥀 </p>
</template>
 
<style scoped>
.shopping-cart-icon{
  font-size: 2rem;
}
</style>