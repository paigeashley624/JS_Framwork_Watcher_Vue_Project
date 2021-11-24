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
  </div>
</template>

<style>
.box {
  background-color: blue;
  height: 100px;
  width: 100px;
}
</style>

<script>
// import axios from "axios";

export default {
  data() {
    return {
      greeting: "Lets Get the Vue Going",
      isVisible: false, //true
    };
  },

  methods: {
    toggleBox() {
      this.isVisible = !this.isVisible;
    },
    greet() {
      console.log(this.greeting);
    },
  },
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
};
</script>
