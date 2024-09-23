<script setup>
import { ref } from 'vue'
const header = ref('App lista de compras')
const items = ref([
{ id: '0', label: 'bolillos'}, 
 {id: '1', label: 'Preentreno'}, 
 { id: '2', label: '1 Nutella'}])
</script>

<template>
  <H1>
    <i class="material-icons shopping-cart-icon"> local_mall</i>
    {{ header }}
    <ul>
      <li v-for="item in items" :key="item">📬 {{ item.label }}</li>
    </ul>
  </H1>
</template>

<style scoped>
.shopping-cart-icon {
  font-size: 2rem;
}
</style>
