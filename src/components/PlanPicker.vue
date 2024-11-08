<script setup>
import PlanPickerItem from './PlanPickerItem.vue';
import {ref} from 'vue';
const plans = ref (['El cafetero', 'Amigo', 'El lechero']);

</script>


<template>

    <div class="plans">
      <PlanPickerItem v-for="plan in plans" :key="plan" :name="plan"> </PlanPickerItem>         
    </div>   

</template>



<style scoped>

</style>