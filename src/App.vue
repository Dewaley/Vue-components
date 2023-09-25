<script setup>
import AlertDialog from "./components/AlertDialog.vue";
import DisplayButtons from "./components/DisplayButtons.vue";
import DisplayAlert from "./components/DisplayAlert.vue";
import { ref } from "vue";

// const alert = ref(false);
const header = `Are you ready?`;
const message = `Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit animi inventore sunt molestiae ut, aspernatur distinctio eius eos? Corrupti hic cumque nemo natus odit ducimus inventore dolore officiis debitis distinctio.`;
const buttonContent = "Yes, I am";
const action = () => alert("Hello");
</script>

<template>
  <main>
    <h1>Vue components</h1>
    <p>
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Natus autem
      incidunt exercitationem est assumenda nemo quam esse enim ad sint?
    </p>
    <DisplayButtons />
    <DisplayAlert />
  </main>
</template>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
  padding: 2rem;
}
</style>
