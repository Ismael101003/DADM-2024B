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
  <h1> <i class="material-icons shopping-cart-icon">local_mall</i> {{ header }}</h1>
<input type="text" placeholder="Add Item" v-model.trim="newItem">
<!-- Radio Buttons -->
<label><input type="radio" v-model="newItemPriority" value="low">Low</label>
<label><input type="radio" v-model="newItemPriority" value="high">High</label>
{{ newItem }}
<ul>
  <li v-for="{ id, label } in items" v-bind:key="id">
    🔹 {{ label }}
  </li>
</ul>
    
</template>

<style scoped>
.shopping-cart-icon {
  font-size: 2rem;
}
</style>