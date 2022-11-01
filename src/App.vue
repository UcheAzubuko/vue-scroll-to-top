<template>
  <section class="app-container">
    <AppButton />
    <NewsList />
  </section>
</template>

<script>
import AppButton from "./components/AppButton.vue";
import NewsList from "./components/NewsList.vue";

export default {
  name: "App",

  components: {
    AppButton,
    NewsList,
  },

  setup() {
    return{}
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Nunito&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font: inherit;
}
html {
  font-family: "Nunito", sans-serif;
}
body {
  font-size: 15px;
  color: #000000;
  background: #fff;
}
h1,
h2,
h3,
h4,
h5,
h6 {
  color: #000000;
}
img {
  max-width: 100%;
}
ul {
  list-style: none;
}
a {
  text-decoration: none;
  display: inline-block;
}
.app-container {
  max-width: 82rem;
  margin: auto;
  padding: 3rem 1rem;
}
</style>
