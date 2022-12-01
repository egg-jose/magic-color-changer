<template>
  <div class="container" :style="{background: color}">
    <Card @change-random-color="changeRandomColor" :color="color" />
  </div>
</template>

<script>
import Card from "./components/Card.vue";

export default {
  name: "App",
  data() {
    return {
      color: "#ffffaa",
    };
  },
  components: {
    Card,
  },
  methods: {
    changeRandomColor() {
      this.color = "#" + Math.floor(Math.random()*16777215).toString(16);
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Lexend+Deca&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: "Lexend Deca", sans-serif;
  color: #2c3e50;
}
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.btn {
  display: inline-block;
  background: #0a2847;
  color: #e9e9e9;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:active {
  transform: scale(0.98);
}
</style>
