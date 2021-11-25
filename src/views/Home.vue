<template>
  <div class="home">
    <canvas id="myChart" width="400" height="400"></canvas>
    <h1>
      Welcome to Javascript Framework Watcher: Stars, Watchers, and Forks https://github.com/acltc/js-framework-watcher
    </h1>
    <h2 v-for="info in repoData" :key="info.id">
      <!-- "info" could be named anything -->
      Name: {{ info.full_name }} Stars: {{ info.stargazers_count }} Watchers: {{ info.watchers_count }} Forks:
      {{ info.forks_count }}
    </h2>
  </div>
</template>
<style></style>

<script>
import axios from "axios";
// import Chart from "chart.js";

export default {
  data() {
    return {
      repoData: [], // this is an empty array until line 33 inserts information
    };
  },
  mounted() {
    this.getRepo("https://api.github.com/repos/vuejs/vue");
    this.getRepo("https://api.github.com/repos/angular/angular.js");
    this.getRepo("https://api.github.com/repos/emberjs/ember.js");
    this.getRepo("https://api.github.com/repos/sveltejs/svelte");
    this.getRepo("https://api.github.com/repos/facebook/react");
  },

  methods: {
    getRepo(url) {
      axios
        .get(url)
        .then((response) => {
          //response is whaever data the api returns
          console.log(response.data); //.data
          this.repoData = [...this.repoData, response.data];
          console.log(this.repoData);
        })
        .catch((error) => {
          console.log(error);
          this.repoData = {};
        });
    },
  },
};
</script>
