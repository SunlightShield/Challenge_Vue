<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'
import 'bootstrap/dist/css/bootstrap.min.css'
import 'bootstrap'
import Form from './components/Form.vue'
import Result from './components/Result.vue'
import Card from './components/Card.vue'
import './main.css'
const datosRecibidos = ref(null)

const recibirDatos = (payment) => {
  console.log('Datos recibidos en el componente padre:', payment)
  datosRecibidos.value = payment
}
</script>

<template>
  <div class="container mt-5" id="containerPrincipal">
    <div class="row">
      <div class="card-header">
        <h4 class="my-0 font-weight-normal mb-3" id="tituloFormulario">Simula tu crédito</h4>
        <div class="card">
          <Form @datos-enviados="recibirDatos" />
        </div>
      </div>
    </div>

    <!-- resultado -->

    <transition name="fade">
      <div v-if="datosRecibidos !== null" class="container mt-5" id="containerPrincipal">
        <div class="row">
          <div class="card-header">
            <h4 class="my-0 font-weight-normal mb-3" id="tituloFormulario">Resultado</h4>
            <!-- Agregar la clase para la animación fadeIn -->
            <div class="card fadeIn">
              <Result :datos="datosRecibidos" />
            </div>
          </div>
        </div>
      </div>
    </transition>
    <div class="row">
      <div class="card">
        <Card />
      </div>
    </div>
    <div class="align-item bottom d-flex flex-row-reverse" id="imagen">
      <img src="./assets/img/fondo.png" />
    </div>
  </div>
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
