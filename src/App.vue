<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'
import 'bootstrap/dist/css/bootstrap.min.css'
import 'bootstrap'
import Form from './components/Form.vue'
import Result from './components/Result.vue'
import Card from './components/Card.vue'
import './main.css'
const dataFromSon = ref(null)
const showForm = ref(true)

const getData = (payment) => {
  console.log('Datos recibidos en el componente padre:', payment)
  dataFromSon.value = payment
  // Ocultar el formulario cuando se reciben datos
  showForm.value = false
}
</script>

<template>
  <div class="container mt-5" id="containerPrincipal">
    <div class="row">
      <!-- Mostrar el formulario solo si showForm es verdadero -->
      <div v-if="showForm" class="card-header">
        <h4 class="my-0 font-weight-normal mb-3" id="tituloFormulario">Simula tu crédito</h4>
        <div class="card">
          <Form @datos-enviados="getData" />
        </div>
      </div>
    </div>

    <!-- resultado -->

    <transition name="fade">
      <div v-if="dataFromSon !== null" class="container mt-5" id="containerPrincipal">
        <div class="row">
          <div class="card-header">
            <h4 class="my-0 font-weight-normal mb-3" id="tituloFormulario">Resultados</h4>
            <div class="card fadeIn">
              <Result :datos="dataFromSon" />
            </div>
          </div>
        </div>
      </div>
    </transition>
    <!-- card api -->
    <transition name="fade">
      <div v-if="dataFromSon !== null" class="container mt-5">
        <div class="row">
          <h4 class="my-0 font-weight-normal mb-3" id="tituloFormulario">Información</h4>
          <div class="card fadeIn">
            <Card />
          </div>
        </div>
      </div>
    </transition>
  </div>
  <!-- <div class="align-item bottom d-flex flex-row-reverse" id="imagen">
    <img src="./assets/img/fondo.png" />
  </div> -->
</template>

<style>
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s; /* Duración de la transición */
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.fadeIn {
  animation: fadeIn 1s;
}
</style>
