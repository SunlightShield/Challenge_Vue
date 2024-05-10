<script setup>
import { ref } from 'vue'
import axios from 'axios'

const banks = ref({}) // Variable bancos
const creditSelected = ref(null) // Variable para darle el producto al modal
const ModalOpen = ref(false) // Variable que comprueba si el modal esta abierto o no

//ejecuto la api proporcionada, algunos de los arrays del json eran diferentes en estructura,
//ocupo un ternario para juzgar si el array es o no igual a los demas usando la variable bankData
//si no lo es, se crea un array para que tengan la misma estructura
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
  creditSelected.value = product
  ModalOpen.value = true
}

// cerrar el modal
const closeModal = () => {
  creditSelected.value = null
  ModalOpen.value = false
}
</script>

<template>
  <div class="container p-5">
    <div class="card-header">
      <h4 class="my-0 font-weight-normal text-center mb-2">Informacion de creditos hipotecarios</h4>
    </div>
    <!-- Iteración de bancos y productos -->
    <div class="row justify-content-center mt-2">
      <!-- primera iteracion para obtener los nombres de los bancos -->
      <div class="col-md-6" v-for="(bankProducts, bankName) in banks" :key="bankName">
        <div class="card mb-4 shadow-sm">
          <div class="card-header">
            <h4 class="my-0 font-weight-normal text-center">{{ bankName }}</h4>
          </div>
          <div class="card-body">
            <div class="card-body d-flex justify-content-center flex-wrap">
              <!-- segunda iteracion para imprimir un boton segun cada credito que aparezca en el array -->
              <div v-for="(product, index) in bankProducts" :key="index">
                <button
                  type="button"
                  class="btn btn-primary p-2 m-2"
                  id="btn-calcular"
                  @click="showModal(product)"
                >
                  Ver Detalles
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Modal -->
    <div class="modal" tabindex="-1" role="dialog" :class="{ show: ModalOpen }">
      <div class="modal-dialog" role="document" id="modal">
        <div class="modal-content">
          <div class="modal-header">
            <h3>Detalles del crédito</h3>
          </div>
          <div class="modal-body">
            <!-- Mostrar cada dato del producto -->
            <p class="card-text">
              Características: {{ creditSelected ? creditSelected.caracteristicas : '' }}
            </p>
            <p class="card-text">
              Costo Total: {{ creditSelected ? creditSelected.costoTotal : '' }}
            </p>
            <p class="card-text">
              Financiamiento: {{ creditSelected ? creditSelected.financiamiento : '' }}
            </p>
            <p class="card-text">
              Gastos Operacionales: {{ creditSelected ? creditSelected.gastosOperacionales : '' }}
            </p>
            <p class="card-text">
              Gastos Operacionales Detalle:
              {{ creditSelected ? creditSelected.gastosOperacionalesText : '' }}
            </p>
            <p class="card-text">
              Plazo Máximo: {{ creditSelected ? creditSelected.maximoPlazo : '' }}
            </p>
            <p class="card-text">
              Observaciones: {{ creditSelected ? creditSelected.observaciones : '' }}
            </p>
            <p class="card-text">
              Periodo De Gracia: {{ creditSelected ? creditSelected.periodoDeGracia : '' }}
            </p>
            <p class="card-text">
              Requisitos: {{ creditSelected ? creditSelected.requisitos : '' }}
            </p>
            <p class="card-text">
              Seguros Incluidos: {{ creditSelected ? creditSelected.segurosIncluidos : '' }}
            </p>
            <p class="card-text">
              Tasa De Interés: {{ creditSelected ? creditSelected.tasaDeInteres : '' }}
            </p>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" id="btn-calcular" @click="closeModal">
              Cerrar
            </button>
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
