<template>
  <section>
    <h1>Buttons</h1>
    <div class="buttons">
      <Button>Default</Button>
      <Button type="primary">Primary</Button>
      <Button type="secondary">Secondary</Button>
      <Button type="success">Success</Button>
      <Button type="danger">Danger</Button>
      <Button type="danger" :left-icon="TrashIcon">Delete</Button>
      <Button type="danger" :right-icon="TrashIcon">Delete</Button>
      <Button type="primary" @clicked="clickedFn">Click me!</Button>
    </div>
  </section>
</template>

<script setup>
import Button from "./Button.vue";
import { TrashIcon } from "@heroicons/vue/24/outline";

const clickedFn = () => alert("I was clicked");
</script>

<style scoped>
section {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
}
.buttons {
  display: flex;
  justify-content: center;
  gap: 1rem;
  flex-wrap: wrap;
  width: 40rem;
}
.code-block {
  font-size: 1.5rem;
  width: 100%;
}
</style>
