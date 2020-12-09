<template>
  <button @click="$emit('click')" type="button">
    <slot></slot>
    {{ label }}
    <slot name="after"></slot>
  </button>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: "",
    },
  },
};
</script>

<style scoped>
button {
  margin: 0.25rem 0;
  width: 120px;
  height: 35px;
  border: 0;
  border-radius: 0.25rem;
  outline: none;
  cursor: pointer;
}
</style>
