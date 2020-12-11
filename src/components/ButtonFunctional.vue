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
    const Prefix = h("i", { class: ["fas", "fa-search"] });
    return h(
      "Button",
      {
        ...ctx.data,
        props: {
          ...ctx.props,
          /** use props or extend here */
        },
      },
      [Prefix],
      ...(ctx.children || [])
    );
  },
};
</script>

