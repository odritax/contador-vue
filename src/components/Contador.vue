<template>
  <div >
   <h3>Contador de click's</h3>
   <p>Número de cliks: {{this.cont}}</p>
   <button  v-on:click="Contar">Contar</button>
  </div>
</template>

<script>
export default {
        name: "Contador",

    data: function() {
        return {
            cont: 0
        }
    },
   mounted: function(){
     //cuando se monte el codigo es como un document ready
     const cont_anterior = localStorage.getItem("cont");
        if (cont_anterior != null) {
            this.cont = cont_anterior;
        }
   },
  methods: {
      Contar: function() {
         this.cont=parseInt(this.cont);
         this.cont += 1;
         localStorage.setItem("cont", this.cont);
        console.log(this.cont);
      }
    }
}

</script>
<style scoped>
</style>
