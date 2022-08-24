<template>
<div>
  <h1 style="color:green;text-align:center">Example app!</h1>
  <div style="margin: auto;">
      <button style="background-color:bisque;" @click='traerDatos'>Get data</button>
</div>
  
  <p v-if="traerDatos">{{datos}}</p>
  <p v-else>No data at the moment</p>
  </div>
  <div class="card">
  <div class="card-body">
    This is some text within a card body.
  </div>
</div>

</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      datos: ''
    }
  },
  name: 'HelloWorld',
  methods: {
    traerDatos() {
      axios.get('https://4mcialxzt9.execute-api.us-east-1.amazonaws.com/default/cindy_caos')
        .then(response => {
          console.log(response)
          this.datos = response.data
        })
        .catch(error => {
          console.log(error)
        })    
  },
}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
