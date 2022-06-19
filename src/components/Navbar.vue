<template>
  <nav class="navbar bg-light">
    <div class="container-fluid">
      <form class="d-flex" role="search">
        <button class="btn btn-outline-success" type="submit">NAVBAR: Recargar pagina para testear funcionalidades</button>
      </form>
    </div>
  </nav>
</template>

<script>
export default {
  props: {
    title: {
      type: String
    }
  },
  data() {
    return {
      search: ''
    }
  },
  methods: {
    searchMovie() {
      this.$emit('search', this.search)
    }
  }
}
</script>