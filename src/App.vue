<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'
import 'bootstrap/dist/css/bootstrap.min.css'
import 'bootstrap'
import Form from './components/Form.vue'
import Result from './components/Result.vue'
import Card from './components/Card.vue'
import './main.css'
const dataFromChild = ref(null) //data que se obtiene del componente Form
const showForm = ref(true) //variable que permite que se vea el modal

const getData = (payment) => {
  console.log('Datos recibidos en el componente padre:', payment)
  dataFromChild.value = payment
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
      <div v-if="dataFromChild !== null" class="container mt-5" id="containerPrincipal">
        <div class="row">
          <div class="card-header">
            <h4 class="my-0 font-weight-normal mb-3" id="tituloFormulario">Resultados</h4>
            <div class="card fadeIn">
              <Result :datos="dataFromChild" />
            </div>
          </div>
        </div>
      </div>
    </transition>

    <!-- card api -->

    <transition name="fade">
      <div v-if="dataFromChild !== null" class="container mt-5">
        <div class="row">
          <h4 class="my-0 font-weight-normal mb-3" id="tituloFormulario">Información</h4>
          <div class="card fadeIn">
            <Card />
          </div>
        </div>
      </div>
    </transition>
  </div>
</template>
