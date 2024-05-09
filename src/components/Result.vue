<script>
export default {
  data() {
    return {
      tiempo: 1, // Ajusta estos valores según tus datos
      totalValue: 10000,
      initialPayment: 1000,
      interest: 5,
      pagoMensual: 0, // Se actualizará después del cálculo
      totalPagado: 0 // Se actualizará después del cálculo
    }
  },
  mounted() {
    // Calcula el pago mensual y el total pagado durante el plazo del préstamo
    this.calcularPagos()
  },
  methods: {
    calcularPagos() {
      const monto = this.totalValue - this.initialPayment
      const tasa = this.interest / 100 / 12
      const tiempoMeses = this.tiempo * 12

      // Calcula el pago mensual utilizando la fórmula del préstamo hipotecario
      const numerador = monto * tasa * Math.pow(1 + tasa, tiempoMeses)
      const denominador = Math.pow(1 + tasa, tiempoMeses) - 1
      this.pagoMensual = numerador / denominador

      // Calcula el total de pagos durante el plazo del préstamo
      this.totalPagado = this.pagoMensual * tiempoMeses
    }
  }
}
</script>

<template>
  <div>
    <h2>Resultados</h2>
    <div>
      <p>Años {{ tiempo }}</p>
      <p>Valor Total de la Propiedad: {{ totalValue }} UF</p>
      <p>Pie {{ initialPayment }} UF</p>
      <p>Interés {{ interest }} %</p>
      <p>Pago Mensual {{ pagoMensual.toFixed(2) }} UF</p>
      <p>
        Total del credito:
        {{ totalPagado.toFixed(2) }} $
      </p>
    </div>
  </div>
</template>
