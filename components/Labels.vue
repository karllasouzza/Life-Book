<template>
  <button>
    {{ text }}
  </button>
</template>

<script>
export default {
  props: {
    text: {
      required: true,
      type: String,
      default: '',
    },
  },
}
</script>

<style scoped>
button {
  font-size: 16px;
  font-weight: bold;

  border: none;
  background: transparent;
  color: var(--primary);
} 
</style>
