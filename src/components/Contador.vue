<template>
  <div >
   <h3>Contador de click's</h3>
   <p>Número de cliks: {{ cont }}</p>
   <button v-on:click="Contar()">click!</button>
  </div>
</template>

<script>
export default {
    name: "Contador",
    methods: {
      Contar() {
        this.$store.commit('increment')
      }
    },
   computed: {
    cont() {
      return this.$store.state.cont
    }
  }    
}

</script>
<style scoped>
</style>
