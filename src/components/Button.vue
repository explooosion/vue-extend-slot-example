<template>
  <button
    v-on="$listeners"
    v-bind="$attrs"
    :type="type"
    :style="`font-weight: ${bold ? 'bold' : 'normal'}`"
    @click="$emit('greet', 'Hello Vue')"
  >
    <slot></slot>
    {{ label }}
    <slot name="after"></slot>
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    type: {
      type: String,
      default: "button",
    },
    label: {
      type: String,
      default: "",
    },
    bold: {
      type: Boolean,
      default: false,
    },
  },
};
</script>
