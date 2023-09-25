<script setup>
import { computed } from "vue";

const props = defineProps({
  leftIcon: Object,
  rightIcon: Object,
  loading: Boolean,
  disabled: Boolean,
  type: String,
});
const emit = defineEmits(["clicked"]);
const classes = computed(() => {
  return props.type;
});
</script>

<template>
  <button
    :disabled="disabled"
    @click="$emit('clicked')"
    class="btn"
    :class="classes"
  >
    <component :is="props.leftIcon" class="icon" />
    <slot />
    <component :is="props.rightIcon" class="icon" />
  </button>
</template>

<style scoped>
.btn {
  padding: 6px 12px;
  font-size: 15px;
  background-color: transparent;
  color: black;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 6px;
  border: 1px solid;
  border-radius: 4px;
  cursor: pointer;
  font-weight: 600;
}
.icon {
  height: 20px;
}
.primary,
.secondary,
.danger,
.success,
.grey {
  border: transparent;
  color: white;
}
.primary {
  background-color: #0d6efd;
}
.secondary {
  background-color: #6c757d;
}
.danger {
  background-color: #dc3545;
}
.success {
  background-color: #198754;
}
.grey {
  background-color: #ececef;
  color: #5C5F68;
}
</style>
