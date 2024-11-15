<script setup>
import PlanPickerItem from './PlanPickerItem.vue';
import {ref} from 'vue';
//Creando una referencia reactiva para almancenar el plan seleccionado
const selectedPlan=ref(null)
const plans = ref (['El cafetero', 'Amigo', 'El lechero']);
const selectPlan = (name) => {
  //Almacenar el plan seleccionado
  selectedPlan.value = name;

};

</script>


<template>

    <div class="plans">
      <PlanPickerItem 
         v-for="plan in plans" 
         :key="plan" 
         :name="plan"
         @select="selectPlan"
         :select-plan="selectedPlan" />       
    </div>   

</template>

  <p> {{ selectedPlan }} </p>



<style scoped>

</style>