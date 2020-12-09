<template>
  <Button
    :label="label"
    v-on="$listeners"
    v-bind="[$attrs, $options.propsData]"
  >
    <template #after>$</template>
  </Button>
</template>

<script>
import Button from "./Button";

export default {
  extends: Button,
  components: {
    Button,
  },
  props: {
    label: {
      type: String,
      default: "Submit",
    },
  },
  mounted() {},
};
</script>

