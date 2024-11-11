<template>
    <div @click="selectPlan" class="plan">
      <div class="description">
        <span class="title">  {{ name }} {{ selected ? '⭐' : '' }} </span>
      </div>
    </div>
  </template>
  
  <script setup>
  //Importar ref función
  import { ref } from 'vue';
  // Usando un macro psrs definir propiedades
  //Son programas o funciones que están disponibles para los otros y no son necesarios importarlos 
  //defineProps(['name','planIcon']); //Para establecer nombres de propiedades siempre usar mayucula en la primer letra de la segunda palabra
  //El sigueinte es un ejemplo de esquema definit¿do
  const props = defineProps({
    name: {
    type: String,
    required: true
  },
  });

  //Definiendo evento
  const emit = defineEmits(['select']);

  //Variable que permite recordar si el plan ha sido seleccionado
  const selected = ref(false);
  //Función que permite cambiar el estado de la variable selected
  const selectPlan = () => {
    selected.value = true;
  
  //Emitir evento de que el plan ha sido seleccionado
  emit('select, props.name');
};

  
  </script>
  
  <style scoped>
  
  </style>