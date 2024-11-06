<template>
    <div class="plan">
      <div class="description">
        <span class="title">
          {{ name }}
        </span>
      </div>
    </div>
  </template>
  
  <script setup>

  // Usando un macro psrs definir propiedades
  //Son programas o funciones que están disponibles para los otros y no son necesarios importarlos 
  //defineProps(['name','planIcon']); //Para establecer nombres de propiedades siempre usar mayucula en la primer letra de la segunda palabra
  //El sigueinte es un ejemplo de esquema definit¿do
  defineProps({
    name: {
    type: String,
    required: true
  },
  });

  
  </script>
  
  <style scoped>
  
  </style>