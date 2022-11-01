<template>
  <button ref="appButton" class="app-button">
    <font-awesome-icon icon="fa-solid fa-arrow-up" />
  </button>
</template>

<script>
import { onMounted, ref, onBeforeMount } from "vue";

export default {
  name: "AppButton",

  setup() {
    const appButton = ref();

    const userScroll = () => {
      if (window.scrollY > 0) {
        appButton.value.classList.add("showButton");
        console.log('scrolled');
      } else {
        appButton.value.classList.remove("showButton");
        console.log('top');
      }
    };

    onMounted(() => {
      window.addEventListener("scroll", userScroll);
    });

    onBeforeMount(() => {
      window.removeEventListener("scroll", userScroll);
    });

    return { appButton };
  },
};
</script>

<style scoped>
.app-button {
  border-radius: 50%;
  height: 50px;
  width: 50px;
  padding: 4px;
  box-shadow: 2px 2px #e9e9e9;
  cursor: pointer;
  position: fixed;
  bottom: 40px;
  display: none;
  right: 40px;
}

.showButton {
  display: block;
}
</style>
