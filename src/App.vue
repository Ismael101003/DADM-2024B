<script setup>
import { ref } from 'vue'
const header = ref('App lista de compras')
</script>

<template>
  <H1>
    <i class="material-icons shopping-cart-icon"> local_mall</i>
    {{ header }}
  </H1>
</template>

<style scoped>
.shopping-cart-icon {
  font-size: 2rem;
}
</style>
