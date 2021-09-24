<template>
  <div>
    <input :type="type" />
    <span v-if="hiden == 'true'">{{ text }}</span>
  </div>
</template>

<script>
export default {
  props: {
    type: {
      required: true,
      type: String,
      default: 'text',
    },
    hiden: {
      required: false,
      type: String,
      default: 'false',
    },
  },
  data() {
    return {
      text: 'Mostrar',
    }
  },
}
</script>

<style scoped>
div {
  width: 100%;
  height: 35px;

  position: relative;
}

div > input {
  width: 100%;
  height: 35px;

  border: none;
  border-bottom: 2px var(--third) solid;
  opacity: 0.5;
}

div > span {
  position: absolute;
  right: 0;

  color: var(--second);
  font-weight: bold;
}

input:active,
input:hover,
input:focus {
  opacity: 1;
  border-bottom: 2px var(--second) solid;
}
</style>
