<script setup>
import { ref } from 'vue'
const header = ref('App lista de compras')
const items = ref([
  { id: '0', label: 'bolillos' },
  { id: '1', label: 'Preentreno' },
  { id: '2', label: '1 Nutella' }
])
const newItem = ref('');
const newitemPriority = ref('low'); 
</script>

<template>
  <H1>
    <i class="material-icons shopping-cart-icon"> local_mall</i>
    {{ header }}
  </H1>
    <ul>
      <li v-for="item in items" :key="item">📬 {{ item.label }}</li>
    <input v-model="newItem" type="text" placeholder="Agregar producto">
    <label><input type="radio" value="low" v-model="newitemPriority"> baja</label>
    <label><input type="radio" value="hight" v-model="newitemPriority"> Alta</label>    
  </ul>
    
</template>

<style scoped>
.shopping-cart-icon {
  font-size: 2rem;
}
</style>
