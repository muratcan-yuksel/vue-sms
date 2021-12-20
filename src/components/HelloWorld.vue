<template>
  <div>
    <button @click="handleClick">Say Hello via SMS!</button>
    <p>{{ status }}</p>
  </div>
</template>

<script>
// const axios = require("axios");
export default {
  name: `HelloWorld`,
  data() {
    return {
      status: "",
    };
  },
  methods: {
    async handleClick() {
      const response = await fetch("https://vue-sms-9504.twil.io/sms");
      const data = await response.json();
      this.status = data.status;
    },
  },
};
</script>

<style>
button {
  color: #000;
  padding: 15px 10px;
  border: 1px solid black;
  border-radius: 3px;
}

button:hover {
  color: #fff;
  background: navy;
}
</style>
