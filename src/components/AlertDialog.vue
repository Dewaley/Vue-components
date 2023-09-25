<script setup>
import { ref, computed } from "vue";
import Button from "./Button.vue";

const props = defineProps({
  state: Boolean,
  message: String,
  dialog: Boolean,
  header: String,
  buttonContent: String,
});

const emit = defineEmits(["action", "close"]);
const closeAlert = () => (visible.value = false);
const classes = computed(() => {
  return props.type;
});
const visibleAlert = computed(() => {
  if (props.state) return "alert-container active";
  else return "alert-container";
});
console.log(classes.value);
</script>

<template>
  <div v-if="props.state" :class="visibleAlert">
    <div class="alert">
      <h2>{{ props.header }}</h2>
      <p>{{ props.message }}</p>
      <div class="btns">
        <Button type="grey" @click="$emit('close')">Cancel</Button>
        <Button type="success" v-if="props.dialog" @click="$emit('action')">
          {{ props.buttonContent }}
        </Button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.alert-container {
  height: 100dvh;
  width: 100dvw;
  position: absolute;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgba(0, 0, 0, 0.3);
}
.alert {
  background-color: #fff;
  width: 90dvw;
  max-width: 500px;
  padding: 20px 15px;
  border-radius: 10px;
  font-size: 15px;
  display: flex;
  flex-direction: column;
  gap: 15px;
}

h2 {
  font-size: 20px;
  /* margin-top: 10px; */
}
.btns {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-end;
  gap: 12.5px;
}
</style>
