<template>
  <div class="card text-bg-dark bg-dark mb-3 text-white" style="max-width: 18rem">
    <div class="card-header">{{ title }}</div>
    <div class="card-body">
      <h5 class="card-title">Fecha: {{ fecha }}</h5>
      <p class="card-text">${{ precio }}</p>
      <p>Cantidad comprada: {{ cantidadComprada }}</p>
      <p>Recaudacion: {{ recaudacion }}</p>
      <p>Total de entradas disponibles: {{ cantidadRestantes }}</p>
      <button @Click="comprarEntrada()" class="btn btn-success">Comprar</button>
      <div class="alert alert-danger p-2 mt-4" role="alert" v-if="disponible === 0">
        Entradas agotadas
      </div>
      <div class="alert alert-warning p-2 mt-4" role="alert" v-else-if="disponible <= 5">
        Últimas {{ cantidadRestantes - cantidadComprada }} entradas disponibles
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    fecha: String,
    precio: Number,
  },
  data() {
    return {
      cantidadComprada: 0,
      cantidadRestantes: 10,
    };
  },
  computed: {
    recaudacion() {
      return this.cantidadComprada * this.precio;
    },
    disponible() {
      return this.cantidadRestantes - this.cantidadComprada;
    },
    bordeindicador() {
      if (this.disponible === 0) {
        return "border-danger";
      }
      else if (this.disponible <= 5) {
        return "border-warning";
      }
      else {
        return "";
      }
    },
  },
  methods: {
    comprarEntrada() {
      if (this.cantidadComprada < this.cantidadRestantes) {
        this.cantidadComprada += 1;
      }
      else {
        alert("No hay entradas disponibles");
      }
    },
  },
};
</script>
