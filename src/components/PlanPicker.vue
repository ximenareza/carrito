<script setup>
import PlanPickerItem from './PlanPickerItem.vue';
import {ref} from 'vue';
const plans = ref (['El cafetero', 'Amigo', 'El lechero']);
const selectPlan = (name) => {
  console.log(name);
};

</script>


<template>

    <div class="plans">
      <PlanPickerItem 
         v-for="plan in plans" 
         :key="plan" 
         :name="plan"
         @select="(name)=>{console.log(name)}"/>       
    </div>   

</template>



<style scoped>

</style>