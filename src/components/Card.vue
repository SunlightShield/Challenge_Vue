<script setup>
import { ref } from 'vue'
import axios from 'axios'

// Variable bancos
const banks = ref({})
// Variable para darle el producto al modal
const selectedProduct = ref(null)
// Variable que comprueba si el modal esta abierto o no
const ModalOpen = ref(false)

axios
  .get('https://api.hipotecarios.info/creditos/?valorPropiedad=2000&Pie=30&Tiempo=20&Dfl2=true')
  .then((response) => {
    for (const [bankName, bankData] of Object.entries(response.data)) {
      banks.value[bankName] = Array.isArray(bankData) ? bankData : [bankData]
    }
  })
  .catch((error) => {
    console.error('Hubo un error al obtener los datos:', error)
  })

//mostrar el modal
const showModal = (product) => {
  selectedProduct.value = product
  ModalOpen.value = true
}

// cerrar el modal
const closeModal = () => {
  selectedProduct.value = null
  ModalOpen.value = false
}
</script>

<template>
  <div class="container">
    <!-- Iteración de bancos y productos -->
    <div class="col-md-4" v-for="(bankProducts, bankName) in banks" :key="bankName">
      <div class="card mb-4 shadow-sm">
        <!-- Línea roja -->
        <div class="card-header">
          <h4 class="my-0 font-weight-normal">{{ bankName }}</h4>
        </div>
        <div class="card-body">
          <div v-for="(product, index) in bankProducts" :key="index">
            <button type="button" class="btn btn-primary" @click="showModal(product)">
              Ver Detalles
            </button>
          </div>
        </div>
      </div>
    </div>

    <!-- Modal -->
    <div class="modal" tabindex="-1" role="dialog" :class="{ show: ModalOpen }">
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <h3>Detalles del crédito</h3>
          </div>
          <div class="modal-body">
            <!-- Mostrar cada dato del producto -->
            <p class="card-text">
              Características: {{ selectedProduct ? selectedProduct.caracteristicas : '' }}
            </p>
            <p class="card-text">
              Costo Total: {{ selectedProduct ? selectedProduct.costoTotal : '' }}
            </p>
            <p class="card-text">
              Financiamiento: {{ selectedProduct ? selectedProduct.financiamiento : '' }}
            </p>
            <p class="card-text">
              Gastos Operacionales: {{ selectedProduct ? selectedProduct.gastosOperacionales : '' }}
            </p>
            <p class="card-text">
              Gastos Operacionales Detalle:
              {{ selectedProduct ? selectedProduct.gastosOperacionalesText : '' }}
            </p>
            <p class="card-text">
              Plazo Máximo: {{ selectedProduct ? selectedProduct.maximoPlazo : '' }}
            </p>
            <p class="card-text">
              Observaciones: {{ selectedProduct ? selectedProduct.observaciones : '' }}
            </p>
            <p class="card-text">
              Periodo De Gracia: {{ selectedProduct ? selectedProduct.periodoDeGracia : '' }}
            </p>
            <p class="card-text">
              Requisitos: {{ selectedProduct ? selectedProduct.requisitos : '' }}
            </p>
            <p class="card-text">
              Seguros Incluidos: {{ selectedProduct ? selectedProduct.segurosIncluidos : '' }}
            </p>
            <p class="card-text">
              Tasa De Interés: {{ selectedProduct ? selectedProduct.tasaDeInteres : '' }}
            </p>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" @click="closeModal">Cerrar</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.modal.show {
  display: block;
}
</style>
