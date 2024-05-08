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

const time = ref(0) //plazo capturado del formulario
const totalValue = ref(0) //valor de la propiedad capturado del formulario
const initialPayment = ref(0) //pie capturado del formulario
const Interest = ref('5') //interes capturado del formulario

const CapturarDatos = () => {
  console.log('Time:', time.value)
  console.log('Valor Total:', totalValue.value)
  console.log('Pago Inicial:', initialPayment.value)
  console.log('Interest:', Interest.value)

  const dividendoHipotecario = calcularDividendoHipotecario(
    time.value,
    totalValue.value,
    initialPayment.value,
    Interest.value
  )
  console.log('Dividendo Hipotecario:', dividendoHipotecario)
}

const calcularDividendoHipotecario = (time, totalValue, initialPayment, Interest) => {
  //parseo todos los datos para obligarlos a ser numeros
  const timeParsed = parseInt(time)
  const totalValueParsed = parseInt(totalValue)
  const initialPaymentParsed = parseInt(initialPayment)
  const interestParsed = parseInt(Interest)

  //verificar que tanto plazo, valor y pie no sean 0
  if (timeParsed === 0 || totalValueParsed === 0 || initialPaymentParsed === 0) {
    console.error('los datos no pueden ser ceros')
  }

  const loan = totalValueParsed - initialPaymentParsed //re resta el pie del total
  const finalInterest = interestParsed / 100 / 12 // se pasa el interes a decimal, y luego se divide en 12
  const paymentPerMonth = loan * (finalInterest / (1 - Math.pow(1 + finalInterest, -timeParsed)))
  console.log('el pago mensual seria de ' + parseInt(paymentPerMonth))
}

// Llamada inicial a CapturarDatos
CapturarDatos()
</script>
<template>
  <form @submit.prevent="handleSubmit">
    <div class="container">
      <div class="mb-3">
        <label for="ValorPorpiedad" class="form-label">Valor Propiedad (en UF)</label>
        <input type="Number" class="form-control" v-model="totalValue" placeholder="100000" />
      </div>
      <div class="mb-3">
        <label for="Pie" class="form-label">Pie (en UF)</label>
        <input
          type="Number"
          class="form-control"
          id="Pie"
          v-model="initialPayment"
          placeholder="100000"
        />
      </div>
      <div class="mb-3">
        <label for="Interes" class="form-label">Tasa de Interés (por defecto 5%)</label>
        <input
          type="Number"
          class="form-control disabled"
          id="tasaInteres"
          v-model="Interest"
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
