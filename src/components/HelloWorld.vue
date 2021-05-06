<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <hr />
    <p>{{ firstNameInCaps }}</p>
    <p>{{ codeAsComputed }}</p>

    <hr />

    <button @click="clickHandler('120')">Click Here!</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

const year = 2021;

export default defineComponent({
  name: "HelloWorld",
  data() {
    return {
      firstName: "Vivek",
      code: year,
    };
  },
  computed: {
    firstNameInCaps(): string {
      return this.firstName.toUpperCase();
    },
    codeAsComputed(): string {
      if (this.code) {
        return this.code.toString();
      } else {
        return "NA";
      }
    },
  },
  props: {
    msg: String,
  },
  methods: {
    clickHandler(factor: number): void {
      console.log("factor", factor, typeof factor);
    },
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
