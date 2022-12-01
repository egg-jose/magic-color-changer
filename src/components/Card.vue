<template>
  <div class="card">
    <h3>Change magic color</h3>
    <Button @btn-click="$emit('change-random-color')" text="Click me!" />
    <span @click="copyURL(color)" class="colorText">{{ color }}</span>
  </div>
</template>

<script>
import Button from "./Button";

export default {
  name: "Card",
  props: {
    color: String,
  },
  components: {
    Button,
  },
  methods: {
  async copyURL(mytext) {
    await navigator.clipboard.writeText(mytext);
    alert('Copied');
  }
}
};
</script>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  text-align: center;
  border: 8px solid #0a2847;
  border-radius: 20px;
  padding: 40px;
  background-color: #f0ffff;
}
h3 {
  margin-bottom: 10px;
}
.colorText {
  margin-top: 10px;
  border: 3px solid #0a2847;
  border-radius: 10px;
  padding: 5px;
  text-align: center;
}
.colorText:hover {
  cursor: pointer;
  background-color: #c2c7c7;
}
</style>
