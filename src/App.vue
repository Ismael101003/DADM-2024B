<script setup>
import { ref } from 'vue'
const header = ref('App Lista de compras')
//Items
//Item model

const items = ref([
  { id: 1, label: '10 bolillos' },
  { id: 2, label: '1 lata de frijoles' },
  { id: 3, label: '2 lata de atún' },
  { id: 4, label: 'Preentreno' },
  { id: 5, label: 'Mancuernas' }
])
//item metod
const saveItem = () => {
  items.value.push({ id: items.value.length + 1, label: newItem.value })
  newItem.value = ''
}
// Formulario
const newItem = ref('')
const newItemHighPriority = ref(false)
const editing = ref(true)

//eventos
const ActivatedEdition = (activated) => {
  editing.value = activated
}
</script>

<template>
  <div class="header">
    <h1>
    <i class="material-icons shopping-cart-icon"> local_mall </i> 
    {{ header }} 
    </h1>
    <button v-if="editing" class="btn" @click="ActivatedEdition(false)">Cancelar</button>
    <button v-else class="btn btn-primary" @click="ActivatedEdition(true)">Agregar articulo</button>
  </div>

  <!--colocando un hiperlink-->
  <a :href="newItem.trim() === '' ? 'https://www.google.com' : 'https://' + newItem" target="_blank">
    {{ newItem.trim() === '' ? 'GOOGLE' : newItem }}
</a>




  <form class="add-item form" v-if="editing" v-on:submit.prevent="saveItem">
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
  <p v-if="items.length === 0">🥀No hay elementos en la lista🥀</p>
  
</template>

<style scoped>
.shopping-cart-icon {
  font-size: 2rem;
}
</style>
