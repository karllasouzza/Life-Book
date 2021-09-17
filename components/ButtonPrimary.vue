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
  width: 80%;
  height: 50px;

  border: none;
  border-radius: 10px;

  background: var(--second);
  color: var(--primary);

  font-size: 18px;
  font-weight: bold;

  padding: 5px;
}
</style>
