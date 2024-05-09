<script setup>
import { ref, defineEmits } from 'vue'
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
const emits = defineEmits(['datos-enviados'])
const time = ref(0) //plazo capturado del formulario
const totalValue = ref(0) //valor de la propiedad capturado del formulario
const initialPayment = ref(0) //pie capturado del formulario
const Interest = ref('5') //interes capturado del formulario}
const paymentPerMonth = ref(0)

const CapturateData = () => {
  console.log('Time:', time.value)
  console.log('Valor Total:', totalValue.value)
  console.log('Pago Inicial:', initialPayment.value)
  console.log('Interest:', Interest.value)

  //enviar datos al metodo para calcular el pago mensual
  const calculate = calculatePayment(
    time.value,
    totalValue.value,
    initialPayment.value,
    Interest.value
  )
}

const calculatePayment = (time, totalValue, initialPayment, interest) => {
  // forzar los datos a ser INT
  const timeParsed = parseInt(time)
  const totalValueParsed = parseInt(totalValue)
  const initialPaymentParsed = parseInt(initialPayment)
  const interestParsed = parseInt(interest)

  // Validar que los datos no sean ceros
  if (timeParsed === 0 || totalValueParsed === 0 || initialPaymentParsed === 0) {
    console.error('los datos no pueden ser ceros')
  }
  const loan = totalValueParsed - initialPaymentParsed
  const monthlyInterest = interestParsed / 100 / 12
  const paymentPerMonth =
    loan * (monthlyInterest / (1 - Math.pow(1 + monthlyInterest, -timeParsed)))

  emitirDatos(
    paymentPerMonth,
    timeParsed,
    totalValueParsed,
    initialPaymentParsed,
    interestParsed,
    loan
  )
}

const emitirDatos = (
  paymentPerMonth,
  timeParsed,
  totalValueParsed,
  initialPaymentParsed,
  interestParsed,
  loan
) => {
  console.log('Datos enviados desde el componente hijo:', paymentPerMonth)
  emits('datos-enviados', {
    payment: parseInt(paymentPerMonth),
    time: timeParsed,
    totalValue: totalValueParsed,
    initialPayment: initialPaymentParsed,
    interest: interestParsed,
    loan: loan
  })
}
</script>
<template>
  <form @submit.prevent="handleSubmit">
    <div class="container p-3">
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

      <button type="submit" class="btn" id="btn-calcular" @click="(e) => CapturateData(e)">
        {{ textoBoton }}
      </button>
    </div>
  </form>
</template>
