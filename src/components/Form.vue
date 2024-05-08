<script setup>
import { ref } from 'vue'
const props = defineProps({
  formFields: {
    type: Array,
    required: true
  },
  textoBoton: {
    type: String,
    default: 'Calcular!'
  }
})

let time = ref(0) //plazo capturado del formulario

const CapturarDatos = () => {
  console.log('Time:', time.value)
}
</script>
<template>
  <form @submit.prevent="handleSubmit">
    <div class="container">
      <div class="mb-3">
        <label for="ValorPorpiedad" class="form-label">Valor Propiedad (en UF)</label>
        <input type="Number" class="form-control" v-model="ValorPorpiedad" placeholder="100000" />
      </div>
      <div class="mb-3">
        <label for="Pie" class="form-label">Pie (en UF)</label>
        <input type="Number" class="form-control" id="Pie" v-model="Pie" placeholder="100000" />
      </div>
      <div class="mb-3">
        <label for="Interes" class="form-label">Tasa de Interés (por defecto 5%)</label>
        <input
          type="Number"
          class="form-control disabled"
          id="tasaInteres"
          v-model="Interes"
          placeholder="5%"
        />
      </div>
      <div class="mb-3">
        <label for="Plazo" class="form-label">Plazo (en años)</label>
        <input type="Number" class="form-control" id="plazo" v-model="time" placeholder="2" />
      </div>

      <button type="submit" class="btn btn-primary" @click="(e) => CapturarDatos(e)">
        {{ textoBoton }}
      </button>
    </div>
  </form>
</template>
