<script>
import axios from 'axios'
import { ref } from 'vue'

//props para hacer el objeto obligatorio
export default {
  props: {
    datos: {
      type: Object,
      required: true
    }
  },
  setup() {
    //setup se ejecuta una vez que componente aparece en el dom
    const uf = ref(null)
    axios
      .get('https://mindicador.cl/api/uf')
      .then((response) => {
        const firstPosition = response.data.serie[0]
        uf.value = firstPosition.valor // obtengo el primer valor del js y se lo paso a la variable uf
      })
      .catch((error) => {
        console.error('Hubo un error al obtener los datos:', error)
      })

    return {
      uf // Retornamos uf para que esté disponible en la plantilla
    }
  }
}
</script>

<template>
  <div class="container">
    <div class="row">
      <!-- card resultado -->
      <div class="col-md-6">
        <div class="p-4">
          <div class="card p-4">
            <div id="textoResultado">
              <!-- toLocaleString para formatear todos los numeros -->
              <p>
                Años:
                {{
                  datos.time.toLocaleString({ minimumFractionDigits: 3, maximumFractionDigits: 3 })
                }}
              </p>
              <p>
                Valor Total de la Propiedad:
                {{
                  datos.totalValue.toLocaleString({
                    minimumFractionDigits: 3,
                    maximumFractionDigits: 3
                  })
                }}
                UF
              </p>
              <p>
                Pie:
                {{
                  datos.initialPayment.toLocaleString({
                    minimumFractionDigits: 3,
                    maximumFractionDigits: 3
                  })
                }}
                UF
              </p>
              <p>
                Interés:
                {{
                  datos.interest.toLocaleString({
                    minimumFractionDigits: 3,
                    maximumFractionDigits: 3
                  })
                }}
                %
              </p>
              <p>
                Pago Mensual: $
                {{
                  ((datos.payment / 12) * uf).toLocaleString({
                    minimumFractionDigits: 3,
                    maximumFractionDigits: 3
                  })
                }}
              </p>
              <p>
                Total del crédito:
                {{
                  datos.loan.toLocaleString({ minimumFractionDigits: 3, maximumFractionDigits: 3 })
                }}
                en UF
              </p>
              <p>
                Sueldo requerido: $
                {{
                  ((datos.payment * uf * 4) / 12).toLocaleString({
                    minimumFractionDigits: 3,
                    maximumFractionDigits: 3
                  })
                }}
              </p>
              <p>
                *Si el sueldo no aparece, por favor espere a que la api que obtiene el valor de la
                uf termine de cargarse
              </p>
            </div>
          </div>
        </div>
      </div>

      <!-- card uf -->
      <div class="col-md-6">
        <div class="p-4">
          <div class="card p-4" v-if="uf !== null">
            <div id="textoResultado">
              <p>
                Valor UF:
                {{
                  uf.toLocaleString({
                    minimumFractionDigits: 3,
                    maximumFractionDigits: 3
                  })
                }}
              </p>
              <p>*Valor de la UF obtenido de la api "https://mindicador.cl/api/uf"</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
