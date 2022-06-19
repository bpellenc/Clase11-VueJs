<template>
  <div class="container">
    <Navbar title="OFERTAS PARA EL MUNDIAL" />
    <h1>Venta de entradas</h1>
    <div class="row">
      <div v-for="entrada in entradasJSON" class="col-md-4">
        <Entrada :title="entrada.descripcion" :fecha="entrada.fecha" :precio="entrada.precio" />
      </div>
    </div>
  </div>
</template>

<script>
import Entrada from "./components/Entrada.vue";
import Navbar from "./components/Navbar.vue";
export default {
  components: {
    Entrada,
    Navbar,
  },
  data() {
    return {
      entradasJSON: [
        {
          descripcion: "Argentina vs Brasil",
          precio: 5000,
          fecha: "1 de diciembre"
        },
        {
          descripcion: "Argentina vs Qatar",
          precio: 6000,
          fecha: "1 de diciembre"
        },
        {
          descripcion: "Argentina vs Alemania",
          precio: 7000,
          fecha: "1 de diciembre"
        },
        {
          descripcion: "Argentina vs Uruguay",
          precio: 7000,
          fecha: "1 de diciembre"
        }
      ]
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
