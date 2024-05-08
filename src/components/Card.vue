<script setup>
import { ref } from 'vue'
import 'bootstrap/dist/css/bootstrap.min.css'
import 'bootstrap'
import axios from 'axios'

const banks = ref()

axios
  .get('https://api.hipotecarios.info/creditos/?valorPropiedad=2000&Pie=30&Tiempo=20&Dfl2=true')
  .then((response) => {
    console.log(response.data) // Agregamos esta línea para imprimir los datos en la consola
    banks.value = response.data
  })
  .catch((error) => {
    console.error('Hubo un error al obtener los datos:', error)
  })
</script>

<template>
  <div class="container">
    <!-- Iterar sobre los bancos dentro de banks -->
    <div class="col-md-4" v-for="(bankData, bankName) in banks" :key="bankName">
      <div class="card mb-4 shadow-sm">
        <div class="card-header">
          <!-- Usar bankName como nombre del banco -->
          <h4 class="my-0 font-weight-normal">{{ bankName }}</h4>
        </div>
        <div class="card-body">
          <!-- Iterar sobre los productos dentro de cada banco -->
          <div v-for="(product, index) in bankData" :key="index">
            <!-- Mostrar información del producto -->
            <p class="card-text">Características: {{ product.caracteristicas }}</p>
            <p class="card-text">Costo Total: {{ product.costoTotal }}</p>
            <p class="card-text">Financiamiento: {{ product.financiamiento }}</p>
            <p class="card-text">Gastos Operacionales: {{ product.gastosOperacionales }}</p>
            <p class="card-text">
              Gastos Operacionales Detalle: {{ product.gastosOperacionalesText }}
            </p>
            <p class="card-text">Plazo Máximo: {{ product.maximoPlazo }}</p>
            <p class="card-text">Observaciones: {{ product.observaciones }}</p>
            <p class="card-text">Periodo De Gracia: {{ product.periodoDeGracia }}</p>
            <p class="card-text">Requisitos: {{ product.requisitos }}</p>
            <p class="card-text">Seguros Incluidos: {{ product.segurosIncluidos }}</p>
            <p class="card-text">Tasa De Interés: {{ product.tasaDeInteres }}</p>
            <!-- Continuar con el resto de la información -->
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
