<template>
  <div class="about">
    <h1>{{ greeting }}</h1>
    <input v-model="greeting" />
    <hr />
    <button v-on:click="toggleBox">Toggle Box</button>
    <!-- the toggleBox in on click is referencing the methos toggleBox -->
    <div v-if="isVisible" class="box"></div>
    <input v-on:keyup.enter="greet" />
    <!-- .enter is a modifier and there are more modifiers -->
    <canvas id="myChart" width="400" height="400"></canvas>
  </div>
</template>

<style>
.box {
  background-color: blue;
  height: 100px;
  width: 100px;
}
</style>

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script>
// import axios from "axios";

export default {
  data() {
    return {
      type: "line",
      data: data,
      options: {},
    };
  },
};
let labels = ["January", "February", "March", "April", "May", "June"];
let data = {
  labels: labels,
  datasets: [
    {
      label: "My First dataset",
      backgroundColor: "rgb(255, 99, 132)",
      borderColor: "rgb(255, 99, 132)",
      data: [0, 10, 5, 2, 20, 30, 45],
    },
  ],
};

const myChart = new Chart(document.getElementById("myChart"), config);

// data() {
//   return {
//     greeting: "Lets Get the Vue Going",
//     isVisible: false, //true
//   };
// },
// methods: {
//   toggleBox() {
//     this.isVisible = !this.isVisible;
//   },
//   greet() {
//     console.log(this.greeting);
//   },
// },
// beforeCreate() {
//   console.log("beforeCreate", this);
// },
// created() {
//   console.log("created");
// },
// beforeMount() {
//   console.log("beforeMount");
// },
// mounted() {
//   console.log("mounted");
// },
// beforeUpdate() {
//   console.log("beforUpdate");
// },
// updated() {
//   console.log("updated");
// },
// beforeDestroy() {
//   console.log("beforeDestroy");
// },
// destroyed() {
//   console.log("destroy");
// },
// };
</script>
