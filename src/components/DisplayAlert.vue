<script setup>
import AlertDialog from "./AlertDialog.vue";
import Button from "./Button.vue";
import { reactive } from "vue";

const alertDialog = reactive({
  state: false,
});

const toggleAlert1 = () => {
  alertDialog.state = true;
  alertDialog.message =
    "Lorem ipsum dolor sit amet consectetur adipisicing elit. Suscipit, voluptatem amet impedit doloremque tempore id ipsa sapiente autem eum! Sit autem pariatur neque officiis obcaecati labore provident animi temporibus dolorem?";
  alertDialog.header = "Are you sure you want to sleep?";
};

const toggleAlert2 = () => {
  alertDialog.state = true;
  alertDialog.message =
    "Lorem ipsum dolor sit amet consectetur adipisicing elit. Suscipit, voluptatem amet impedit doloremque tempore id ipsa sapiente autem eum! Sit autem pariatur neque officiis obcaecati labore provident animi temporibus dolorem?";
  alertDialog.header = "Are you ready?";
  alertDialog.dialog = true;
  alertDialog.buttonContent = "Yes, I am";
};

const close = () => {
  alertDialog.state = false;
  alertDialog.message = "";
  alertDialog.header = "";
  alertDialog.dialog = false;
  alertDialog.buttonContent = "";
};
const action = () => {
  alert("Hiii");
  close();
};
</script>

<template>
  <section>
    <h3>Alert Dialog</h3>
    <div class="alert-container">
      <Button type="primary" @clicked="toggleAlert1"> Open Alert </Button>
      <Button type="primary" @clicked="toggleAlert2">
        Open Alert Dialog
      </Button>
      <AlertDialog
        :state="alertDialog.state"
        :message="alertDialog.message"
        :header="alertDialog.header"
        :dialog="alertDialog.dialog"
        :buttonContent="alertDialog.buttonContent"
        @action="action"
        @close="close"
      />
    </div>
  </section>
</template>

<style scoped>
section {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
}
.alert-container {
  display: flex;
  justify-content: center;
  gap: 1rem;
  flex-wrap: wrap;
}
</style>
