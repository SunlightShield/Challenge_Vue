<script setup>
import { defineProps } from 'vue'

const props = defineProps({
  datos: Object // Definir el tipo de datos que esperas recibir
})
</script>

<template>
  <div>
    <!-- Mostrar los datos recibidos -->
    <pre>{{ datos }}</pre>
  </div>
</template>
