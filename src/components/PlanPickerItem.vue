<template>
    <div @click="selectPlan" class="plan">
      <div class="description">
        <span class="title">  {{ name }} {{ isSelected ? '⭐' : '' }} </span>
      </div>
    </div>
  </template>
  
  <script setup>
  //Importamos la función para crear propiedad computada
  import { computed } from 'vue';

  // Usando un macro psrs definir propiedades
  //Son programas o funciones que están disponibles para los otros y no son necesarios importarlos 
  //defineProps(['name','planIcon']); //Para establecer nombres de propiedades siempre usar mayucula en la primer letra de la segunda palabra
  //El sigueinte es un ejemplo de esquema definit¿do
  const props = defineProps({
    name: {
    type: String,
    required: true
    },
    selectPlan: String
  });

  //Definiendo evento
  const emit = defineEmits(['select']);

  //Función que permite cambiar el estado de la variable selected
  const selectPlan = () => {

  
  //Emitir evento de que el plan ha sido seleccionado
  emit('select', props.name);
};
//Creaando una propiedad computada para saber si el plan ha sido seleccionado
const isSelected = computed(() => {
  return props.name === props.selectedPlan;
})

  
  </script>
  
  <style scoped>
  
  </style>