<template>
  <h1>{{ title }}</h1>
  <div v-if="showModel">
    <Model :header="header" :text="text"  theme="sale" @close="toggleModel" />
  </div>
  <p>Welcome...</p>
  <button @click="toggleModel">Open Model</button>
  
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Model from "./components/Model.vue";

export default {
  name: "App",
  component: { Model },
  data() {
    return {
      title: "My first vue App :)",
      header: "Sign up for the giveaway!",
      text: "Hurry Up!",
      showModel: false
    };
  },
  methods: {
    handleClick() {
      let ref = this.$refs.name;
      ref.style.display = "inline-block";
      ref.classList.add("active");
      ref.focus();
    },
    toggleModel() {
      this.showModel = !this.showModel;
    }
  },
  components: { Model },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  border-bottom: 1px solid rgb(156, 155, 155);
  display: inline-block;
  padding-bottom: 10px;
}
</style>
