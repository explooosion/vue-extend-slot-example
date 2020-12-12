<script>
import Button from "./Button";

export default {
  extends: Button,
  functional: true,
  props: {
    label: {
      type: String,
      default: "Search",
    },
  },
  render(h, ctx) {
    return h(
      "Button",
      {
        ...ctx.data,
        props: {
          ...ctx.props,
          /** use props or extend here */
        },
        scopedSlots: {
          ...ctx.scopedSlots,
          default: () => h("i", { class: ["fas", "fa-search"] }),
          /** use slots or extend here */
        },
      },
      ...(ctx.children || [])
    );
  },
};
</script>

