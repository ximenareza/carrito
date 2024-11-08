<script setup>
import planItem from './plan-item.vue';
import {ref} from 'vue';
const plans = ref (['El cafetero', 'Amigo', 'El lechero']);

</script>


<template>

    <div class="plans">
      <plan-item v-for="plan in plans" :key="plan" :name="plan"> </plan-item>         
    </div>   

</template>



<style scoped>

</style>