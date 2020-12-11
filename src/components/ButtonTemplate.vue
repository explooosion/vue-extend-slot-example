<template>
  <Button
    :label="label"
    :type="type"
    v-on="$listeners"
    v-bind="[$attrs, $options.propsData]"
  >
    <template #after><i class="fas fa-redo"></i></template>
    <template v-for="(_, slot) of $scopedSlots" v-slot:[slot]="scope">
      <slot :name="slot" v-bind="scope" />
    </template>
  </Button>
</template>

<script>
import Button from "./Button";

export default {
  name: "ButtonTemplate",
  components: {
    Button,
  },
  props: {
    ...Button.props,
    type: {
      type: String,
      default: "reset",
    },
    label: {
      type: String,
      default: "Reset",
    },
  },
};
</script>

