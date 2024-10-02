<script setup>
import { ref } from 'vue'
const header = ref('App Lista de compras')
//Items
//Item model

const items = ref([
  { id: 1, label: '10 bolillos' },
  { id: 2, label: '1 lata de frijoles' },
  { id: 3, label: '2 lata de atún' },
  { id: 4, label: 'Preentreno' }
])
//item metod
const saveItem = () => {
  items.value.push({ id: items.value.length + 1, label: newItem.value })
  newItem.value='';
}

const newItem = ref('')
const newItemHighPriority = ref(false)
</script>

<template>
  <h1><i class="material-icons shopping-cart-icon">local_mall</i> {{ header }}</h1>

  <form class="add-item form"
   v-on:submit.prevent="saveItem">
    <!-- entrada de texto -->
    <input v-model.trim="newItem" type="text" placeholder="Add Item" />
    <!-- Caja de seleccion de prioridad -->
    <label>
      <input type="checkbox" v-model="newItemHighPriority" />
      High Priority
    </label>
    <!-- Boton -->
    <button class="btn btn-primary">Save Item</button>
  </form>

  <ul>
    <li v-for="{ id, label } in items" v-bind:key="id">🔹 {{ label }}</li>
  </ul>
</template>

<style scoped>
.shopping-cart-icon {
  font-size: 2rem;
}
</style>
