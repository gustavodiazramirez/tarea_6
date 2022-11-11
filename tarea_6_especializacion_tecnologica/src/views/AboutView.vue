<template>
  <div class="TRABAJO 2">
    <p>Tarea de Gustavo Díaz</p>
    <div class="post" v-for="job in jobs" v-bind:key="job._Id">
      <strong> Nombre del trabajo: {{ job.title }}</strong> , Un salario de: {{ job.salary }}
    </div>
    <p class="text-justify" >no logré vincular aplicantes entonnces cumplo con tener una segunda pagina pero de lo mismo</p>
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
