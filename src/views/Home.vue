<template>
  <div class="home">
    <h1>
      Welcome to Javascript Framework Watcher: Stars, Watchers, and Forks https://github.com/acltc/js-framework-watcher
    </h1>
    <h2 v-for="info in repoData" :key="info.id">
      {{ info.full_name }}
      {{ info.forks_count }}
    </h2>
  </div>
</template>
<style></style>

<script>
import axios from "axios";
export default {
  data() {
    return {
      repoData: [],
    };
  },
  mounted() {
    this.getRepo("https://api.github.com/repos/vuejs/vue");
    this.getRepo("https://api.github.com/repos/angular/angular.js");
  },
  created() {},
  methods: {
    getRepo(url) {
      axios
        .get(url)
        .then((response) => {
          console.log(response.data);
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
