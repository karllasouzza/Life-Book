<template>
  <label :for="target">
    {{ text }}
  </label>
</template>

<script>
export default {
  props: {
    text: {
      required: true,
      type: String,
      default: '',
    },
    target: {
      required: true,
      type: String,
      default: '',
    },
  },
}
</script>

<style scoped>
label {
  font-size: 14px;
  font-weight: bold;

  border: none;
  background: transparent;
  color: var(--third);
}
</style>
