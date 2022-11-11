<template>
  <div class="TRABAJOS">
    <p>Tarea de Gustavo Díaz</p>
    <div class="post" v-for="job in jobs" v-bind:key="job._id">
      <strong> Nombre del trabajo: {{ job.title }}</strong> , Un salario de: {{ job.salary }}
    </div>
  </div>
</template>


<script>
import axios from 'axios'
export default {
  name: 'HomeView',
  data() {
    return {
      jobs: []
    }
  },
  mounted() {
    let vue = this;
    axios.get('//170.239.85.65:3000/jobs').then(function (response) {
      vue.jobs = response.data;
      console.log(vue.jobs)
      })
  }
}
</script>
