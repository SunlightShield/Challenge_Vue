<script setup>
import { ref } from 'vue'
import 'bootstrap/dist/css/bootstrap.min.css'
import 'bootstrap'
import axios from 'axios'

const banks = ref({
  'banco-scotiabank': [
    {
      banco: {
        nombre: 'SCOTIABANK'
      },
      tasaDeInteres: '5,51 %',
      costoTotal: '2.426,29 UF',
      gastosOperacionales: '$668.446',
      maximoPlazo: '25 años',
      periodoDeGracia: {
        valor: 'Hasta 6 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '90% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas:
        'Tasa Semi-Variable: Producto variable con tasa fija y conocida durante los primeros 3, 5 y 8 años, que luego de finalizar se vuelven a establecer las tasas para un tiempo de 12 meses, como resultado de la suma del spread más la TAB UF 360 de renovación.',
      requisitos: [
        'Válido para Persona Natural sin giro, chilenos o extranjeros residentes.',
        'Titular, aval o fiador deben tener entre 21 y 80 años y contar con seguro de desgravamen.',
        'Renta mínima para clientes de la región metropolitana $500.000 y para regiones $450.000.',
        'Demostrar contrato indefinido con antigüedad de 1 año en el empleo actual. Para independientes, demostrar 2 años en la actividad actual.',
        'En caso de complementar renta solo se puede hacer con cónyuges, padres, hijos o pareja del titular con hijos en común.',
        'No presentar deuda morosa ni protestos vigentes.',
        'Contar con cédula de identidad vigente.'
      ],
      gastosOperacionalesText: [
        'Tasación: 2.68 UF',
        'Estudio de títulos: 5.92 UF',
        'Gastos legales: 3 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.18%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.004783% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.024753% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Simulación realizada con pie del 20% del monto de la propiedad.',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    },
    {
      banco: {
        nombre: 'SCOTIABANK'
      },
      tasaDeInteres: '5,51 %',
      costoTotal: '2.426,29 UF',
      gastosOperacionales: '$646.438',
      maximoPlazo: '30 años',
      periodoDeGracia: {
        valor: 'Hasta 6 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '80% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas:
        'Crédito Hipotecario Tradicional cuya tasa es fija, por todo el plazo del crédito, permite conocer el valor de los dividendos que regirán por el plazo total del crédito. Disponible solo para créditos de vivienda.',
      requisitos: [
        'Válido para Persona Natural sin giro, chilenos o extranjeros residentes.',
        'Titular, aval o fiador deben tener entre 21 y 80 años y contar con seguro de desgravamen.',
        'Renta mínima para clientes de la región metropolitana $500.000 y para regiones $450.000.',
        'Demostrar contrato indefinido con antigüedad de 1 año en el empleo actual. Para independientes, demostrar 2 años en la actividad actual.',
        'En caso de complementar renta solo se puede hacer con cónyuges, padres, hijos o pareja del titular con hijos en común.',
        'No presentar deuda morosa ni protestos vigentes.',
        'Contar con cédula de identidad vigente.',
        'No ser actualmente propietario de una vivienda ni el postulante ni su cónyuge ni su conviviente civil.',
        'No haber obtenido anteriormente un subsidio habitacional ni el postulante ni su cónyuge ni su conviviente civil.',
        'Haber Completado el ahorro requerido:',
        '-Para postular al título I (tramo 1) UF 30 de ahorro mínimo. Y se puede comprar viviendas de hasta UF 1.000.',
        '-Para postular al Título I (tramo 2) ahorro mínimo de UF 40. Y se puede comprar viviendas de hasta UF 1.400.',
        '-Para postular al titulo II, ahorro mínimo de UF 80. Y se puede comprar viviendas de hasta UF 2.200.'
      ],
      gastosOperacionalesText: [
        'Tasación: 2.25 UF',
        'Estudio de títulos: 5.76 UF',
        'Gastos legales: 3 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.18%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.0058% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.0195% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Simulación realizada con pie del 20% del monto de la propiedad.',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    },
    {
      banco: {
        nombre: 'SCOTIABANK',
        imagen: 'https://d7nxjt1whovz0.cloudfront.net/marketplace/logos/divisions/scotiabank.png'
      },
      tasaDeInteres: '5,79 %',
      costoTotal: '2.479,77 UF',
      gastosOperacionales: '$646.438',
      maximoPlazo: '25 años',
      periodoDeGracia: {
        valor: 'Hasta 6 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '90% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Crédito Hipotecario Tradicional cuya tasa es fija, por todo el plazo del crédito, que permite conocer el valor de los dividendos que regirán por el plazo total del crédito.',
        'Disponible para vivienda y fines generales.',
        'Ajuste del plazo del crédito a la cantidad de meses (cuotas) que el cliente desee, dentro de los plazos establecidos. (entre 5 y 30 años)',
        'Prepago desde el 5% del saldo de la deuda, con comisión de 1,5 meses de interés.',
        'Prepagos permiten reducir plazo o rebajar valor cuota.',
        'Hipoteca especifica y/o general. (general a solicitud del cliente)'
      ],
      requisitos: [
        'Válido para Persona Natural sin giro, chilenos o extranjeros residentes.',
        'Titular, aval o fiador deben tener entre 25 y 79 años y 364 días de edad y contar con seguro de desgravamen.',
        'Renta mínima para clientes de la región metropolitana $500.000 y para regiones $450.000.',
        'Demostrar contrato indefinido con antigüedad de 1 año en el empleo actual. Para independientes, demostrar 2 años en la actividad actual.',
        'En caso de complementar renta solo se puede hacer con cónyuges, padres, hijos o pareja del titular con hijos en común.',
        'No presentar deuda morosa ni protestos vigentes.',
        'Contar con cédula de identidad vigente.'
      ],
      gastosOperacionalesText: [
        'Tasación: 2.25 UF',
        'Estudio de títulos: 5.76 UF',
        'Gastos legales: 3 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.18%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.0058% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.0195% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Simulación realizada con pie del 20% del monto de la propiedad.',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    },
    {
      banco: {
        nombre: 'SCOTIABANK',
        imagen: 'https://d7nxjt1whovz0.cloudfront.net/marketplace/logos/divisions/scotiabank.png'
      },
      tasaDeInteres: '5,79 %',
      costoTotal: '2.479,77 UF',
      gastosOperacionales: '$646.438',
      maximoPlazo: '20 años',
      periodoDeGracia: {
        valor: 'Hasta 6 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '75% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Crédito Hipotecario Tradicional cuya tasa es fija, por todo el plazo del crédito, que permite conocer el valor de los dividendos que regirán por el plazo total del crédito.',
        'Disponible para vivienda y fines generales.',
        'Ajuste del plazo del crédito a la cantidad de meses (cuotas) que el cliente desee, dentro de los plazos establecidos. (entre 5 y 30 años)',
        'Prepago desde el 5% del saldo de la deuda, con comisión de 1,5 meses de interés.',
        'Prepagos permiten reducir plazo o rebajar valor cuota.',
        'Hipoteca especifica y/o general. (general a solicitud del cliente)'
      ],
      requisitos: [
        'Válido para Persona Natural sin giro, chilenos o extranjeros residentes.',
        'Titular, aval o fiador deben tener entre 25 y 79 años y 364 días de edad y contar con seguro de desgravamen.',
        'Renta mínima para clientes de la región metropolitana $500.000 y para regiones $450.000.',
        'Demostrar contrato indefinido con antigüedad de 1 año en el empleo actual. Para independientes, demostrar 2 años en la actividad actual.',
        'En caso de complementar renta solo se puede hacer con cónyuges, padres, hijos o pareja del titular con hijos en común.',
        'No presentar deuda morosa ni protestos vigentes.',
        'Contar con cédula de identidad vigente.'
      ],
      gastosOperacionalesText: [
        'Tasación: 2.25 UF',
        'Estudio de títulos: 5.76 UF',
        'Gastos legales: 3 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.18%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.0058% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.0195% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Simulación realizada con pie del 20% del monto de la propiedad.',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    },
    {
      banco: {
        nombre: 'SCOTIABANK',
        imagen: 'https://d7nxjt1whovz0.cloudfront.net/marketplace/logos/divisions/scotiabank.png'
      },
      tasaDeInteres: '5,51 %',
      costoTotal: '2.426,29 UF',
      gastosOperacionales: '$646.438',
      maximoPlazo: '25 años',
      periodoDeGracia: {
        valor: 'Hasta 6 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '90% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Crédito Hipotecario Tradicional cuya tasa es fija, por todo el plazo del crédito, que permite conocer el valor de los dividendos que regirán por el plazo total del crédito.',
        'Disponible para vivienda y fines generales.',
        'Ajuste del plazo del crédito a la cantidad de meses (cuotas) que el cliente desee, dentro de los plazos establecidos. (entre 5 y 30 años)',
        'Prepago desde el 5% del saldo de la deuda, con comisión de 1,5 meses de interés.',
        'Prepagos permiten reducir plazo o rebajar valor cuota.',
        'Hipoteca especifica y/o general. (general a solicitud del cliente)'
      ],
      requisitos: [
        'Válido para Persona Natural sin giro, chilenos o extranjeros residentes.',
        'Titular, aval o fiador deben tener entre 25 y 79 años y 364 días de edad y contar con seguro de desgravamen.',
        'Renta mínima para clientes de la región metropolitana $500.000 y para regiones $450.000.',
        'Demostrar contrato indefinido con antigüedad de 1 año en el empleo actual. Para independientes, demostrar 2 años en la actividad actual.',
        'En caso de complementar renta solo se puede hacer con cónyuges, padres, hijos o pareja del titular con hijos en común.',
        'No presentar deuda morosa ni protestos vigentes.',
        'Contar con cédula de identidad vigente.'
      ],
      gastosOperacionalesText: [
        'Tasación: 2.25 UF',
        'Estudio de títulos: 5.76 UF',
        'Gastos legales: 3 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.18%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.0058% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.0195% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Simulación realizada con pie del 20% del monto de la propiedad.',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    },
    {
      banco: {
        nombre: 'SCOTIABANK',
        imagen: 'https://d7nxjt1whovz0.cloudfront.net/marketplace/logos/divisions/scotiabank.png'
      },
      tasaDeInteres: '5,51 %',
      costoTotal: '2.426,29 UF',
      gastosOperacionales: '$668.446',
      maximoPlazo: '30 años',
      periodoDeGracia: {
        valor: 'Hasta 6 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '80% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [],
      requisitos: [
        'Válido para Persona Natural sin giro, chilenos o extranjeros residentes.',
        'Titular, aval o fiador deben tener entre 21 y 80 años y contar con seguro de desgravamen.',
        'Renta mínima para clientes de la región metropolitana $500.000 y para regiones $450.000.',
        'Demostrar contrato indefinido con antigüedad de 1 año en el empleo actual. Para independientes, demostrar 2 años en la actividad actual.',
        'En caso de complementar renta solo se puede hacer con cónyuges, padres, hijos o pareja del titular con hijos en común.',
        'No presentar deuda morosa ni protestos vigentes.',
        'Contar con cédula de identidad vigente.'
      ],
      gastosOperacionalesText: [
        'Tasación: 2.68 UF',
        'Estudio de títulos: 5.92 UF',
        'Gastos legales: 3 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.18%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.004783% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.024753% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Simulación realizada con pie del 20% del monto de la propiedad.',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    }
  ],
  'banco-santander': [
    {
      banco: {
        nombre: 'BANCO SANTANDER'
      },
      tasaDeInteres: '6,1 %',
      costoTotal: '2.582,1 UF',
      gastosOperacionales: '$1.223.495',
      maximoPlazo: '30 años',
      periodoDeGracia: {
        valor: 'Hasta 6 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '80% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Plazo de hasta 30 años.',
        'Opción de hasta 6 meses de no pago para cancelar el primer dividendo.',
        'Hasta el 80% de financiamiento, desde UF 200.',
        'Opción de incluir el Subsidio Habitacional.',
        'Opción de tasa fija por todo el periodo del crédito..',
        'Compra de vivienda o fines generales (terreno, oficina, local).'
      ],
      requisitos: [
        'Edad mínima: 21 años.',
        'Edad máxima: 70 años.',
        'Ingresos acreditables y de acuerdo a las políticas de riesgo vigente del banco (para trabajadores dependiente e independiente).',
        'Nacionalidad chilena, o extranjero con residencia definitiva.',
        'Domicilio acreditable.',
        'Dependiendo de cada caso, podría exigirse requisitos distintos a los aquí señalados.'
      ],
      gastosOperacionalesText: [
        'Tasación: 3 UF',
        'Estudio de títulos: 4.2 UF',
        'Redacción escritura: 3.3 UF',
        'Gastos notariales: 3.5 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.8%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.0087% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.026327% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.',
        'En caso de optar al crédito con Subsidio Habitacional, debes contar con Seguro de Cesantía.'
      ],
      observaciones: [
        'Dependiendo de cada caso, podría exigirse requisitos distintos a los aquí señalados.',
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Cálculo realizado con una renta entre $800.000 y $1.300.000',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    },
    {
      banco: {
        nombre: 'BANCO SANTANDER',
        imagen:
          'https://d7nxjt1whovz0.cloudfront.net/marketplace/logos/divisions/banco-santander.png'
      },
      tasaDeInteres: '6,1 %',
      costoTotal: '2.582,1 UF',
      gastosOperacionales: '$1.223.495',
      maximoPlazo: '25 años',
      periodoDeGracia: {
        valor: 'No',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '90% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Créditos a tasa fija en UF durante todo el periodo del crédito.',
        'Únicamente para personas naturales, con destino vivienda, por un monto desde UF 500 hasta UF 5.000.',
        'Plazo del crédito entre 15 y 25 años.',
        'No considera meses de gracia ni meses de no pago.',
        'Debe contar con seguro de Desgravamen e Incendio y Sismo durante toda la vida del crédito.',
        'Puede tomar las pólizas respectivas con la aseguradora que estimes conveniente incluyendo las que ofertamos en nuestras sucursales. Tales seguros deben cumplir con los requisitos de cobertura exigidos por el Banco.'
      ],
      requisitos: [
        'Edad mínima: 21 años.',
        'Edad máxima: 70 años.',
        'Ingresos acreditables y de acuerdo a las políticas de riesgo vigente del banco (para trabajadores dependiente e independiente).',
        'Nacionalidad chilena, o extranjero con residencia definitiva.',
        'Domicilio acreditable.',
        'Dependiendo de cada caso, podría exigirse requisitos distintos a los aquí señalados.'
      ],
      gastosOperacionalesText: [
        'Tasación: 3 UF',
        'Estudio de títulos: 4.2 UF',
        'Redacción escritura: 3.3 UF',
        'Gastos notariales: 3.5 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.8%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.0087% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.026327% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.',
        'En caso de optar al crédito con Subsidio Habitacional, debes contar con Seguro de Cesantía.'
      ],
      observaciones: [
        'Dependiendo de cada caso, podría exigirse requisitos distintos a los aquí señalados.',
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Cálculo realizado con una renta entre $800.000 y $1.300.000',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    },
    {
      banco: {
        nombre: 'BANCO SANTANDER',
        imagen:
          'https://d7nxjt1whovz0.cloudfront.net/marketplace/logos/divisions/banco-santander.png'
      },
      tasaDeInteres: '6,1 %',
      costoTotal: '2.582,1 UF',
      gastosOperacionales: '$1.223.495',
      maximoPlazo: '20 años',
      periodoDeGracia: {
        valor: 'No informado',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '90% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Presente su proyecto a su ejecutivo de cuentas, una vez que el banco realiza la evaluación comercial y ésta es Aprobada, comienza el financiamiento con créditos comerciales de enlace, cuyos montos se van liberando en función del avance el proyecto.',
        'Financiamiento mediante línea de construcción.',
        'Una vez terminada la construcción, y luego de obtener la Recepción Municipal, puedes optar a traspasar esta deuda a un Crédito Hipotecario.',
        'Seguros hipotecarios con excelentes coberturas.',
        'Opción de realizar prepagos en cualquier momento del crédito.'
      ],
      requisitos: [
        'Edad mínima: 21 años.',
        'Edad máxima: 70 años.',
        'Ingresos acreditables y de acuerdo a las políticas de riesgo vigente del banco (para trabajadores dependiente e independiente).',
        'Nacionalidad chilena, o extranjero con residencia definitiva.',
        'Domicilio acreditable.',
        'Dependiendo de cada caso, podría exigirse requisitos distintos a los aquí señalados.'
      ],
      gastosOperacionalesText: [
        'Tasación: 3 UF',
        'Estudio de títulos: 4.2 UF',
        'Redacción escritura: 3.3 UF',
        'Gastos notariales: 3.5 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.8%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.0087% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.026327% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.',
        'En caso de optar al crédito con Subsidio Habitacional, debes contar con Seguro de Cesantía.'
      ],
      observaciones: [
        'Dependiendo de cada caso, podría exigirse requisitos distintos a los aquí señalados.',
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Cálculo realizado con una renta entre $800.000 y $1.300.000',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    }
  ],
  'banco-estado': [
    {
      banco: {
        nombre: 'BANCO ESTADO'
      },
      tasaDeInteres: '5,2 %',
      costoTotal: '2.432,58 UF',
      gastosOperacionales: '$1.078.018',
      maximoPlazo: '30 años',
      periodoDeGracia: {
        valor: 'Hasta 6 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '90% del menor valor entre la tasación y el precio de venta de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Financiamiento hasta 90%\n\n\n    \n\n\n\n            \n\n            \n                \n  \n  \n  \n      Para la compra de propiedades nuevas o usadas, sujeto a evaluación comercial y de riesgo',
        'Plazo de 8 hasta 30 años\n\n\n    \n\n\n\n            \n\n            \n                \n  \n  \n  \n      Dependiendo del tipo de producto, plazos de 8, 12, 15, 20, 25 y 30 años',
        'Hasta 6 meses de gracia\n\n\n    \n\n\n\n            \n\n            \n                \n  \n  \n  \n      Para pagar el primer dividendo',
        'Hasta 2 meses de no pago\n\n\n    \n\n\n\n            \n\n            \n                \n  \n  \n  \n      Durante el año, a partir del segundo año del crédito',
        'Tasa preferencial\n\n\n    \n\n\n\n            \n\n            \n                \n  \n  \n  \n      Al tener o contratar un plan de cuenta y pago automático del dividendo (PAC)',
        'Complementa renta\n\n\n    \n\n\n\n            \n\n            \n                \n  \n  \n  \n      Para optar a un mayor financiamiento'
      ],
      requisitos: [
        '◦ Ser mayor de 18 años.\n\n◦ Tener nacionalidad chilena o extranjera con más de un año de permanencia definitiva.\n\n◦ Tener buenos antecedentes comerciales y ser sujeto de crédito según la Política Crediticia del Banco. \n\n◦ Si eres trabajadores dependientes debes tener antigüedad laboral de a lo menos 1 año o continuidad laboral de a lo menos 6 meses con el actual empleador.',
        '◦ Ser mayor de 18 años.\n\n◦ Tener nacionalidad chilena o extranjera con más de un año de permanencia definitiva.\n\n◦ Tener buenos antecedentes comerciales y ser sujeto de crédito según la Política Crediticia del Banco. \n\n◦ Si eres trabajadores dependientes debes tener antigüedad laboral de a lo menos 1 año o continuidad laboral de a lo menos 6 meses con el actual empleador.'
      ],
      gastosOperacionalesText: [
        'Tasación: 2 UF',
        'Estudio de títulos: 2.9 UF',
        'Redacción escritura: 4.3 UF',
        'Gastos notariales: 2.5 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 1.2% - 0.45%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.0125% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.0283% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Tasas actualizadas el 08 mayo 2024.',
        'Simulación realizada para un crédito con tasa fija.',
        'En BancoEstado la aprobación comercial de un crédito hipotecario tiene una vigencia de 90 días continuos para créditos sin subsidio y 120 días continuos para créditos con subsidio.'
      ]
    },
    {
      banco: {
        nombre: 'BANCO ESTADO'
      },
      tasaDeInteres: '5,2 %',
      costoTotal: '2.432,58 UF',
      gastosOperacionales: '$1.078.018',
      maximoPlazo: '30 años',
      periodoDeGracia: {
        valor: 'Hasta 6 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '90% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Financiamiento hasta 90%\n\n\n    \n\n\n\n            \n\n            \n                \n  \n  \n  \n      Para la compra de propiedades nuevas o usadas, sujeto a evaluación comercial y de riesgo',
        'Plazo de 8 hasta 30 años\n\n\n    \n\n\n\n            \n\n            \n                \n  \n  \n  \n      Dependiendo del tipo de producto, plazos de 8, 12, 15, 20, 25 y 30 años',
        'Hasta 6 meses de gracia\n\n\n    \n\n\n\n            \n\n            \n                \n  \n  \n  \n      Para pagar el primer dividendo',
        'Hasta 2 meses de no pago\n\n\n    \n\n\n\n            \n\n            \n                \n  \n  \n  \n      Durante el año, a partir del segundo año del crédito',
        'Tasa preferencial\n\n\n    \n\n\n\n            \n\n            \n                \n  \n  \n  \n      Al tener o contratar un plan de cuenta y pago automático del dividendo (PAC)',
        'Complementa renta\n\n\n    \n\n\n\n            \n\n            \n                \n  \n  \n  \n      Para optar a un mayor financiamiento'
      ],
      requisitos: [
        'Ser mayor de 18 años y tener buenos antecedentes comerciales',
        'Trabajador Dependiente: tener a lo menos un año de antigüedad laboral',
        'Trabajador Independiente: Para profesionales 1 año desde inicio de actividades y 2 años para técnicos, comisionistas y otras personas prestadoras de servicios.'
      ],
      gastosOperacionalesText: [
        'Tasación: 2 UF',
        'Estudio de títulos: 2.9 UF',
        'Redacción escritura: 4.3 UF',
        'Gastos notariales: 2.5 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 1.2% - 0.45%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.0125% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.0283% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Tasas actualizadas el 08 mayo 2024.',
        'Simulación realizada para un crédito con tasa fija.',
        'En BancoEstado la aprobación comercial de un crédito hipotecario tiene una vigencia de 90 días continuos para créditos sin subsidio y 120 días continuos para créditos con subsidio.'
      ]
    },
    {
      banco: {
        nombre: 'BANCO ESTADO',
        imagen: 'https://d7nxjt1whovz0.cloudfront.net/marketplace/logos/divisions/banco-estado.png'
      },
      tasaDeInteres: '5,2 %',
      costoTotal: '2.432,58 UF',
      gastosOperacionales: '$1.078.018',
      maximoPlazo: '30 años',
      periodoDeGracia: {
        valor: 'Hasta 6 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '90% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Puedes financiar con una tasa preferencial la adquisición de viviendas nuevas de proyectos inmobiliarios que cuenten con Calificación de Eficiencia Energética con letra D o superior (A-B-C), validada por el Ministerio de Vivienda y Urbanismo.',
        'Para financiamiento hasta el 80% puedes escoger plazos de 8, 12, 15, 20, 25 y 30 años.',
        'Para créditos de hasta UF 3.000, financiamiento hasta del 90% (*) y puedes escoger plazos de 8, 12, 15, 20 y 25 años.',
        'Para créditos sin Subsidio, el valor de la vivienda no tiene tope.',
        'Para créditos con Subsidio Habitacional, el precio máximo de la propiedad es de UF 2.600, dependiendo del tipo de subsidio, tramo y zona en la que está ubicada la vivienda.'
      ],
      requisitos: [
        '· Ser mayor de 18 años.',
        '· Buenos antecedentes comerciales.',
        'Trabajador Dependiente:',
        '· Tener a lo menos 1 año de antigüedad laboral.',
        'Trabajador Independiente:',
        '· Tener a lo menos 1 año desde la Iniciación de Actividades, para profesionales.',
        '· Tener a lo menos 2 años desde la Iniciación de Actividades, para técnicos, comisionistas y otras personas prestadoras de servicios.',
        'Antecedentes de la Propiedad:',
        'Financiamiento Compraventas y Créditos de Fines Generales'
      ],
      gastosOperacionalesText: [
        'Tasación: 2 UF',
        'Estudio de títulos: 2.9 UF',
        'Redacción escritura: 4.3 UF',
        'Gastos notariales: 2.5 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 1.2% - 0.45%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.0125% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.0283% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Tasas actualizadas el 08 mayo 2024.',
        'Simulación realizada para un crédito con tasa fija.',
        'En BancoEstado la aprobación comercial de un crédito hipotecario tiene una vigencia de 90 días continuos para créditos sin subsidio y 120 días continuos para créditos con subsidio.'
      ]
    }
  ],
  'banco-falabella': {
    banco: {
      nombre: 'BANCO FALABELLA',
      imagen: 'https://d7nxjt1whovz0.cloudfront.net/marketplace/logos/divisions/banco-falabella.png'
    },
    tasaDeInteres: '5,81 %',
    costoTotal: '2.474,88 UF',
    gastosOperacionales: '$906.431',
    maximoPlazo: '25 años',
    periodoDeGracia: {
      valor: 'Hasta 6 meses',
      descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
    },
    financiamientoHasta: {
      valor: '80% del valor de la propiedad',
      descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
    },
    caracteristicas: [
      'El Crédito Hipotecario Banco Falabella es un préstamo que te permitirá, a mediano o largo plazo, cubrir hasta un 80% del valor de la propiedad que elijas.',
      'Posee un plazo máximo de 25 años.',
      'Podrás financiar la vivienda que siempre quisiste, ya sea nueva o usada.'
    ],
    requisitos: [
      'Ser chileno o extranjero',
      'Acreditar buenos antecedentes financieros y comerciales, y no tener morosidades o protestos vigentes.',
      'Acreditar una antigüedad en el trabajo de 12 meses para empleados y 24 meses para independientes y/o vendedores y comisionistas.',
      'Cumplir los niveles mínimos establecidos en los modelos de riesgo utilizados.'
    ],
    gastosOperacionalesText: [
      'Tasación: 2.5 UF',
      'Estudio de títulos: 2.5 UF',
      'Redacción escritura: 2 UF',
      'Gastos notariales: 2.5 UF',
      'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
      'Conservador de bienes raíces: 0.6%',
      'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
    ],
    segurosIncluidos: [
      'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
      'Seguro de desgravamen: 0.009167% mensual sobre el saldo de la deuda.',
      'Seguro de incendio y sismo: 0% mensual sobre el saldo de la deuda.',
      'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
    ],
    observaciones: [
      'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
      'Tasas actualizadas el 08 mayo 2024. Comunícate con el Banco para mayor información.'
    ]
  },
  'bice-hipotecaria': [
    {
      banco: {
        nombre: 'BICE HIPOTECARIA'
      },
      tasaDeInteres: '5,85 %',
      costoTotal: '2.489,01 UF',
      gastosOperacionales: '$816.907',
      maximoPlazo: '30 años',
      periodoDeGracia: {
        valor: 'Hasta 3 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '90% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Financia Hasta 80% de la propiedad',
        '30 años Plazo Máximo',
        'UF 1.000 Monto mínimo de crédito',
        'Puedes realizar prepagos de carácter parcial dentro de un límite predeterminado e informado en la escritura, los cuales se encuentran exentos del cobro de comisión por tal concepto y se considerarán como abonos directos al capital adeudado, con el objetivo de extinguir sus obligaciones en forma anticipada al plazo estipulado en la escritura.'
      ],
      requisitos: [
        'Edad mínima 23 años cumplidos a la fecha de otorgamiento del crédito.',
        'Personas naturales con residencia definitiva en Chile, sean chilenos o extranjeros.',
        'Plazo del crédito no puede ser inferior a 8 años ni superior a 30 años.',
        'Plazo del crédito no puede ser inferior a 8 años ni superior a 30 años.',
        'Destino del crédito puede ser adquisición de inmuebles, refinanciamiento o fines generales.',
        'Financiamiento máximo:\n\nAdquisición de inmuebles con destino primera vivienda hasta el 80% del menor valor entre tasación y precio de compraventa\nAdquisición de inmuebles con destino no habitacional hasta el 70% del menor valor entre tasación y precio de compraventa\nRefinanciamiento de créditos hasta el 70% del valor de tasación.',
        'Se requerirá la comparecencia de un mandatario para el caso de ausencia o impedimento del deudor.',
        'Deberá contar tanto el deudor como el codeudor con un seguro de desgravamen o de desgravamen e incapacidad total y permanente, según corresponda.'
      ],
      gastosOperacionalesText: [
        'Tasación: 2.5 UF',
        'Estudio de títulos: 2 UF',
        'Redacción escritura: 2 UF',
        'Gastos notariales: 3 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.57% - 0.44%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.015417% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.012333% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.',
        'El costo del seguro de desgravamen es decreciente en el período del crédito, al reducirse el capital adeudado.',
        'Opcionalmente, puedes contratar seguros de invalidez y cesantía.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    },
    {
      banco: {
        nombre: 'BICE HIPOTECARIA',
        imagen:
          'https://d7nxjt1whovz0.cloudfront.net/marketplace/logos/divisions/banco-bice-hipotecaria.png'
      },
      tasaDeInteres: '5,85 %',
      costoTotal: '2.489,01 UF',
      gastosOperacionales: '$816.907',
      maximoPlazo: '30 años',
      periodoDeGracia: {
        valor: 'No informado',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '80% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Financia Hasta 80% de la propiedad',
        '30 años Plazo Máximo',
        '1.000 UF Monto mínimo de crédito',
        'El crédito universal es un tipo de préstamo en dinero que se puede solicitar para efectos de comprar una vivienda a través de un crédito hipotecario que tiene la ventaja de que facilita su comparación y cotización.'
      ],
      requisitos: [
        'Edad mínima 23 años cumplidos a la fecha de otorgamiento del crédito.',
        'Personas naturales con residencia definitiva en Chile, sean chilenos o extranjeros.',
        'Plazo del crédito no puede ser inferior a 8 años ni superior a 30 años.',
        'Plazo del crédito no puede ser inferior a 8 años ni superior a 30 años.',
        'Destino del crédito puede ser adquisición de inmuebles, refinanciamiento o fines generales.',
        'Financiamiento máximo:\n\nAdquisición de inmuebles con destino primera vivienda hasta el 80% del menor valor entre tasación y precio de compraventa\nAdquisición de inmuebles con destino no habitacional hasta el 70% del menor valor entre tasación y precio de compraventa\nRefinanciamiento de créditos hasta el 70% del valor de tasación.',
        'Se requerirá la comparecencia de un mandatario para el caso de ausencia o impedimento del deudor.',
        'Deberá contar tanto el deudor como el codeudor con un seguro de desgravamen o de desgravamen e incapacidad total y permanente, según corresponda.'
      ],
      gastosOperacionalesText: [
        'Tasación: 2.5 UF',
        'Estudio de títulos: 2 UF',
        'Redacción escritura: 2 UF',
        'Gastos notariales: 3 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.57% - 0.44%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.015417% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.012333% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    },
    {
      banco: {
        nombre: 'BICE HIPOTECARIA',
        imagen:
          'https://d7nxjt1whovz0.cloudfront.net/marketplace/logos/divisions/banco-bice-hipotecaria.png'
      },
      tasaDeInteres: '5,85 %',
      costoTotal: '2.489,01 UF',
      gastosOperacionales: '$816.907',
      maximoPlazo: '30 años',
      periodoDeGracia: {
        valor: 'Hasta 3 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '90% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Financia Hasta 80% de la propiedad',
        '30 años Plazo Máximo',
        'UF 1.000 Monto mínimo de crédito',
        'Producto para quienes prefieren un financiamiento tradicional. Se fija una cuota al inicio del crédito en UF y se paga todos los meses la misma cuota.'
      ],
      requisitos: [
        'Edad mínima 23 años cumplidos a la fecha de otorgamiento del crédito.',
        'Personas naturales con residencia definitiva en Chile, sean chilenos o extranjeros.',
        'Plazo del crédito no puede ser inferior a 8 años ni superior a 30 años.',
        'Plazo del crédito no puede ser inferior a 8 años ni superior a 30 años.',
        'Destino del crédito puede ser adquisición de inmuebles, refinanciamiento o fines generales.',
        'Financiamiento máximo:\n\nAdquisición de inmuebles con destino primera vivienda hasta el 80% del menor valor entre tasación y precio de compraventa\nAdquisición de inmuebles con destino no habitacional hasta el 70% del menor valor entre tasación y precio de compraventa\nRefinanciamiento de créditos hasta el 70% del valor de tasación.',
        'Se requerirá la comparecencia de un mandatario para el caso de ausencia o impedimento del deudor.',
        'Deberá contar tanto el deudor como el codeudor con un seguro de desgravamen o de desgravamen e incapacidad total y permanente, según corresponda.'
      ],
      gastosOperacionalesText: [
        'Tasación: 2.5 UF',
        'Estudio de títulos: 2 UF',
        'Redacción escritura: 2 UF',
        'Gastos notariales: 3 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.57% - 0.44%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.015417% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.012333% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.',
        'El costo del seguro de desgravamen es decreciente en el período del crédito, al reducirse el capital adeudado.',
        'Opcionalmente, puedes contratar seguros de invalidez y cesantía.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    },
    {
      banco: {
        nombre: 'BICE HIPOTECARIA',
        imagen:
          'https://d7nxjt1whovz0.cloudfront.net/marketplace/logos/divisions/banco-bice-hipotecaria.png'
      },
      tasaDeInteres: '5,85 %',
      costoTotal: '2.489,01 UF',
      gastosOperacionales: '$816.907',
      maximoPlazo: '30 años',
      periodoDeGracia: {
        valor: 'Hasta 3 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '80% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Financia Hasta 80% de la propiedad',
        '8-30 años Plazo Máximo',
        'UF 1.000 Monto mínimo de crédito',
        'Consiste en un financiamiento para quienes ya tienen un crédito hipotecario vigente y quieren reducir el dividendo, cambiar el plazo o solicitar más capital.'
      ],
      requisitos: [
        'Edad mínima 23 años cumplidos a la fecha de otorgamiento del crédito.',
        'Personas naturales con residencia definitiva en Chile, sean chilenos o extranjeros.',
        'Plazo del crédito no puede ser inferior a 8 años ni superior a 30 años.',
        'Plazo del crédito no puede ser inferior a 8 años ni superior a 30 años.',
        'Destino del crédito puede ser adquisición de inmuebles, refinanciamiento o fines generales.',
        'Financiamiento máximo:\n\nAdquisición de inmuebles con destino primera vivienda hasta el 80% del menor valor entre tasación y precio de compraventa\nAdquisición de inmuebles con destino no habitacional hasta el 70% del menor valor entre tasación y precio de compraventa\nRefinanciamiento de créditos hasta el 70% del valor de tasación.',
        'Se requerirá la comparecencia de un mandatario para el caso de ausencia o impedimento del deudor.',
        'Deberá contar tanto el deudor como el codeudor con un seguro de desgravamen o de desgravamen e incapacidad total y permanente, según corresponda.'
      ],
      gastosOperacionalesText: [
        'Tasación: 2.5 UF',
        'Estudio de títulos: 2 UF',
        'Redacción escritura: 2 UF',
        'Gastos notariales: 3 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.57% - 0.44%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.015417% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.012333% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.',
        'El costo del seguro de desgravamen es decreciente en el período del crédito, al reducirse el capital adeudado.',
        'Opcionalmente, puedes contratar seguros de invalidez y cesantía.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    }
  ],
  'banco-edwards-citi': {
    banco: {
      nombre: 'BANCO EDWARDS CITI'
    },
    tasaDeInteres: '5,99 %',
    costoTotal: '2.510,73 UF',
    gastosOperacionales: '$1.012.367',
    maximoPlazo: '20 años',
    periodoDeGracia: {
      valor: 'Hasta 11 meses',
      descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
    },
    financiamientoHasta: {
      valor: '80% del valor de la propiedad',
      descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
    },
    caracteristicas: [
      'Tasa fija para todo el período de duración del crédito.',
      'Pagarás el mismo dividendo durante toda la vida del préstamo y estarás protegido frente a variaciones del tipo de interés que puedan producirse a futuro.',
      'En caso de prepago, tienes la opción de reestructurar tu crédito de dos formas: disminuir el valor del dividendo, manteniendo el plazo o disminuir el plazo pactado, manteniendo el valor del dividendo.'
    ],
    requisitos: [
      'Fotocopia simple de cédula de identidad (comprador y cónyuge).',
      'Si es casado, tener el certificado de matrimonio al día.',
      'Empleado: 3 últimas liquidaciones, certificado de antigüedad y renta.',
      'Profesional independiente: última declaración de impuesto anual a la renta, fotocopia 6 últimas declaraciones de impuesto mensual y/o boletas de honorarios últimos 3 meses, y fotocopia título profesional.',
      'Si es comerciante industrial o empresario: 2 últimas declaraciones de impuesto anual a la renta. 2 últimos balances autorizados, comprobante de pago de IVA de los últimos 6 meses y certificado otorgado por el contador que acredite retiros de los últimos 6 meses.',
      'Rentista: copia de certificado de dominio vigente de la (las) propiedad(es) por la(s) que obtiene renta. último recibo de contribuciones de sus propiedades, fotocopia de contrato(s) de arriendo, y última declaración de impuesto anual a la renta.'
    ],
    gastosOperacionalesText: [
      'Tasación: 2.98 UF',
      'Estudio de títulos: 6 UF',
      'Gastos legales: 3.2 UF',
      'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
      'Conservador de bienes raíces: 0.64%',
      'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
    ],
    segurosIncluidos: [
      'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
      'Seguro de desgravamen: 0.0071% mensual sobre el saldo de la deuda.',
      'Seguro de incendio y sismo: 0.01704% mensual sobre el saldo de la deuda.',
      'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
    ],
    observaciones: [
      'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
      'Tasas actualizadas el 08 mayo 2024.'
    ]
  },
  'banco-bci': [
    {
      banco: {
        nombre: 'BANCO BCI'
      },
      tasaDeInteres: '5,84 %',
      costoTotal: '2.517,66 UF',
      gastosOperacionales: '$1.465.210',
      maximoPlazo: '30 años',
      periodoDeGracia: {
        valor: 'Hasta 6 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '90% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Destinado para la compra, reparación y construcción de una vivienda o refinanciamiento de créditos hipotecarios existentes.',
        'Fines generales, compra de sitios, compra de oficinas y locales comerciales, y libre disponibilidad.',
        'Plazo del Crédito de 5 a 30 años.',
        'Tasa Fija los primeros años, entre 1 y 5 años del Crédito, y posteriormente tasa variable, la cual se fija año a año en función de la TAB*.',
        'Período de gracia de hasta 6 meses.',
        'Hasta 90% de financiamiento.',
        'Seguros a contratar: Desgravamen, incendio o incendio y sismo.'
      ],
      requisitos: [
        'Requisitos Generales',
        'Tener un sueldo líquido superior a 23 UF ($800.000*) Puedes complementar renta con un codeudor.',
        'El valor del dividendo de la propiedad que comprarás no debe superar el 30% de tu sueldo líquido.',
        'Mantener un buen historial de comportamiento de pago.',
        'Ser cliente de algún banco o tener una línea de crédito con alguna institución financiera por al menos 6 meses.',
        'Chileno o extranjero con residencia definitiva en Chile.',
        'Requisitos para Dependientes',
        'Además de los requisitos generales los dependientes deben:',
        'Tener un contrato de trabajo indefinido.',
        'Contar con una antigüedad laboral mínima de 3 meses con continuidad laboral de un año.',
        'Requisitos para Independientes',
        'Además de los requisitos generales los independientes deben:',
        '12 meses de cotizaciones continuas (profesional universitario).',
        '24 meses de cotizaciones continuas (otros profesionales).'
      ],
      gastosOperacionalesText: [
        'Tasación: 2.12 UF',
        'Estudio de títulos: 2.12 UF',
        'Redacción escritura: 2.12 UF',
        'Gastos notariales: 2.12 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.4% - 0.4%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.0055% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.0256% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Cálculo realizado con una renta entre $600.000 y $1.300.000, y con 4 años de tasa fija.',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    },
    {
      banco: {
        nombre: 'BANCO BCI',
        imagen: 'https://s3.amazonaws.com/marketplace.comparaonline.com/marketplace//bci.png'
      },
      tasaDeInteres: '6,13 %',
      costoTotal: '2.573,84 UF',
      gastosOperacionales: '$1.544.662',
      maximoPlazo: '30 años',
      periodoDeGracia: {
        valor: 'Hasta 6 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '90% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Destinado a la compra de casas, departamentos, oficinas, locales comerciales, etc.',
        'Tasa Fija durante todo el período, en UF o en pesos.',
        'Plazo del Crédito de 5 a 30 años.*',
        'Período de gracia de hasta 6 meses.',
        'Posibilidad de elegir un mes de no pago de dividendo al año.',
        'Prepago: Puedes prepagar parte de la deuda con el fin de disminuir el dividendo, o acortar el plazo residual del Crédito.',
        'Hasta 90% de financiamiento.*',
        'Seguros a contratar: Desgravamen, incendio o incendio y sismo.'
      ],
      requisitos: [
        'Requisitos Generales',
        'Tener un sueldo líquido superior a 23 UF ($800.000*) Puedes complementar renta con un codeudor.',
        'El valor del dividendo de la propiedad que comprarás no debe superar el 30% de tu sueldo líquido.',
        'Mantener un buen historial de comportamiento de pago.',
        'Ser cliente de algún banco o tener una línea de crédito con alguna institución financiera por al menos 6 meses.',
        'Chileno o extranjero con residencia definitiva en Chile.',
        'Requisitos para Dependientes',
        'Además de los requisitos generales los dependientes deben:',
        'Tener un contrato de trabajo indefinido.',
        'Contar con una antigüedad laboral mínima de 3 meses con continuidad laboral de un año.',
        'Requisitos para Independientes',
        'Además de los requisitos generales los independientes deben:',
        '12 meses de cotizaciones continuas (profesional universitario).',
        '24 meses de cotizaciones continuas (otros profesionales).'
      ],
      gastosOperacionalesText: [
        'Tasación: 2.05 UF',
        'Estudio de títulos: 3 UF',
        'Redacción escritura: 3 UF',
        'Gastos notariales: 2.56 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.4% - 0.4%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.0055% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.0256% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Cálculo realizado con una renta entre $600.000 y $1.300.000',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    }
  ],
  'banco-chile': [
    {
      banco: {
        nombre: 'BANCO DE CHILE',
        imagen:
          'https://d7nxjt1whovz0.cloudfront.net/marketplace/logos/divisions/banco-de-chile.png'
      },
      tasaDeInteres: '5,99 %',
      costoTotal: '2.510,73 UF',
      gastosOperacionales: '$1.012.367',
      maximoPlazo: '15 años',
      periodoDeGracia: {
        valor: 'Hasta 11 meses',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '80% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Tasa fija para todo el período de duración del crédito.',
        'Pagarás el mismo dividendo durante toda la vida del préstamo y estarás protegido frente a variaciones del tipo de interés que puedan producirse a futuro.',
        'En caso de prepago, tienes la opción de reestructurar tu crédito de dos formas: disminuir el valor del dividendo, manteniendo el plazo o disminuir el plazo pactado, manteniendo el valor del dividendo.'
      ],
      requisitos: [
        'Fotocopia simple de cédula de identidad (comprador y cónyuge).',
        'Si es casado, tener el certificado de matrimonio al día.',
        'Empleado: 3 últimas liquidaciones, certificado de antigüedad y renta.',
        'Profesional independiente: última declaración de impuesto anual a la renta, fotocopia 6 últimas declaraciones de impuesto mensual y/o boletas de honorarios últimos 3 meses, y fotocopia título profesional.',
        'Si es comerciante industrial o empresario: 2 últimas declaraciones de impuesto anual a la renta. 2 últimos balances autorizados, comprobante de pago de IVA de los últimos 6 meses y certificado otorgado por el contador que acredite retiros de los últimos 6 meses.',
        'Rentista: copia de certificado de dominio vigente de la (las) propiedad(es) por la(s) que obtiene renta. último recibo de contribuciones de sus propiedades, fotocopia de contrato(s) de arriendo, y última declaración de impuesto anual a la renta.'
      ],
      gastosOperacionalesText: [
        'Tasación: 2.98 UF',
        'Estudio de títulos: 6 UF',
        'Gastos legales: 3.2 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.64%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.0071% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.01704% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    }
  ],
  'banco-security': {
    banco: {
      nombre: 'BANCO SECURITY',
      imagen: 'https://d7nxjt1whovz0.cloudfront.net/marketplace/logos/divisions/banco-security.png'
    },
    tasaDeInteres: '5,34 %',
    costoTotal: '2.374,26 UF',
    gastosOperacionales: '$809.446',
    maximoPlazo: '30 años',
    periodoDeGracia: {
      valor: 'Hasta 6 meses',
      descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
    },
    financiamientoHasta: {
      valor: '80% del valor de la propiedad',
      descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
    },
    caracteristicas: [
      'Destino Vivienda o Fines Generales.',
      'Puede fijar la tasa entre 2 y 8 años, resto del periodo es tasa variable, TAB UF 360 días + spread.',
      'Financiamiento hasta el 80% (sujeto a evaluación).',
      'Plazos corridos desde 6 hasta 20 años, luego 25 y 30 años.',
      'Hasta 6 meses de gracia (sujeto a evaluación).',
      'Comisión de prepago según normativa vigente.',
      'Monto mínimo de prepago: 10% del saldo capital.'
    ],
    requisitos: [
      'Nacionalidad Chilena.',
      'Edad mínima de 21 años y máxima de 75 años.',
      'Ingreso fijo mensual líquido declarado y acreditado.',
      'Patrimonio mínimo desde UF 500.',
      'Relación pasivos/patrimonio de hasta 6 veces el patrimonio acreditado y verificado.',
      'No registrar deudas pendientes laborales y/o previsionales.'
    ],
    gastosOperacionalesText: [
      'Tasación: 2.7 UF',
      'Estudio de títulos: 5.5 UF',
      'Gastos legales: 3.5 UF',
      'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL4',
      'Conservador de bienes raíces: 0.36%',
      'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
    ],
    segurosIncluidos: [
      'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
      'Seguro de desgravamen: 0.0056% mensual sobre el saldo de la deuda.',
      'Seguro de incendio y sismo: 0.014553% mensual sobre el saldo de la deuda.',
      'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
    ],
    observaciones: [
      'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
      'Tasas actualizadas el 08 mayo 2024.'
    ]
  },
  'banco-consorcio': [
    {
      banco: {
        nombre: 'BANCO CONSORCIO',
        imagen:
          'https://s3.amazonaws.com/marketplace.comparaonline.com/marketplace/logos/divisions/Consorcio.png'
      },
      tasaDeInteres: '6,1 %',
      costoTotal: '2.561,27 UF',
      gastosOperacionales: '$446.576',
      maximoPlazo: '30 años',
      periodoDeGracia: {
        valor: 'No',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '80% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Simula y solicita tu crédito',
        '100% online',
        'Hasta 30 años plazo',
        'La diferencia de vivir en una casa y vivir en TU casa',
        'Con el Crédito Hipotecario de Banco Consorcio obtén una completa asesoría de ejecutivos especialistas para que tu sueño de la casa propia se haga realidad.'
      ],
      requisitos: [
        'Nacionalidad chilena o extranjera con residencia definitiva mínima de dos años en Chile.',
        'Renta Liquida mínima de $600.000.',
        'Contrato Indefinido, 18 meses en empleo actual o 24 Meses continuidad laboral.',
        'La edad al contratar el crédito más el plazo de este no puede superar los 74 años y 364 días.',
        'Carga financiera máxima no puede superar el 45% de renta líquida total que determine el banco.',
        'Dividendo máximo del crédito solicitado no puede superar el 25% de renta líquida total que determine el banco.',
        'Tipo de bien a financiar: Casas o departamentos.',
        'Valor mínimo de vivienda a financiar: UF 1.000.',
        'Antigüedad máxima de vivienda: 30 años.',
        'La aprobación está sujeta a la política comercial y de riesgo vigente.'
      ],
      gastosOperacionalesText: [
        'Redacción escritura: 2.5 UF',
        'Gastos notariales: 3 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.2%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.0025% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0.016% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    },
    {
      banco: {
        nombre: 'BANCO CONSORCIO',
        imagen:
          'https://s3.amazonaws.com/marketplace.comparaonline.com/marketplace/logos/divisions/Consorcio.png'
      },
      tasaDeInteres: '6,1 %',
      costoTotal: '2.561,27 UF',
      gastosOperacionales: '$446.576',
      maximoPlazo: '30 años',
      periodoDeGracia: {
        valor: 'No',
        descripcion: 'Periodo de tiempo, al inicio del crédito, libre de pago'
      },
      financiamientoHasta: {
        valor: '80% del valor de la propiedad',
        descripcion: 'Máximo porcentaje del valor de la propiedad que se puede pedir en el crédito.'
      },
      caracteristicas: [
        'Simula y solicita tu crédito',
        '100% online',
        'Hasta 30 años plazo',
        'La diferencia de vivir en una casa y vivir en TU casa',
        'Con el Crédito Hipotecario de Banco Consorcio obtén una completa asesoría de ejecutivos especialistas para que tu sueño de la casa propia se haga realidad.'
      ],
      requisitos: [
        'Nacionalidad chilena o extranjera con residencia definitiva mínima de dos años en Chile.',
        'Renta Liquida mínima de $600.000.',
        'Contrato Indefinido, 18 meses en empleo actual o 24 Meses continuidad laboral.',
        'La edad al contratar el crédito más el plazo de este no puede superar los 74 años y 364 días.',
        'Carga financiera máxima no puede superar el 45% de renta líquida total que determine el banco.',
        'Dividendo máximo del crédito solicitado no puede superar el 25% de renta líquida total que determine el banco.',
        'Tipo de bien a financiar: Casas o departamentos.',
        'Valor mínimo de vivienda a financiar: UF 1.000.',
        'Antigüedad máxima de vivienda: 30 años.',
        'La aprobación está sujeta a la política comercial y de riesgo vigente.'
      ],
      gastosOperacionalesText: [
        'Redacción escritura: 2.5 UF',
        'Gastos notariales: 3 UF',
        'Impuesto al mutuo para viviendas con calificación DFL2 es de 0.20% sobre el valor del crédito y 0.80% si la vivienda no califica como DFL2',
        'Conservador de bienes raíces: 0.2%',
        'Gastos operacionales son aproximados, dependen de la institución financiera y la evaluación de la propiedad'
      ],
      segurosIncluidos: [
        'El seguro de desgravamen permite extinguir o eliminar la deuda pendiente con el acreedor y, junto al seguro de incendio, tienen carácter obligatorio. Recuerda revisar en el contrato de los seguros si hay coberturas especiales.',
        'Seguro de desgravamen: 0.0025% mensual sobre el saldo de la deuda.',
        'Seguro de incendio y sismo: 0% mensual sobre el saldo de la deuda.',
        'El seguro de desgravamen y de incendio están incluidos en el cálculo del dividendo total.'
      ],
      observaciones: [
        'Los valores son referenciales, pueden variar dependiendo de tu perfil financiero, la evaluación de la propiedad y las condiciones particulares de la compañía que se encuentren vigentes al momento de la redirección.',
        'Tasas actualizadas el 08 mayo 2024.'
      ]
    }
  ]
})

// axios
//   .get('https://api.hipotecarios.info/creditos/?valorPropiedad=2000&Pie=30&Tiempo=20&Dfl2=true')
//   .then((response) => {
//     console.log(response.data) // Agregamos esta línea para imprimir los datos en la consola
//     banks.value = response.data
//   })
//   .catch((error) => {
//     console.error('Hubo un error al obtener los datos:', error)
//   })
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
