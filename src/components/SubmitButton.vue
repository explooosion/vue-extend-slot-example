<script>
import Button from "./Button";

export default {
  extends: Button,
  functional: true,
  // props: {
  //   label: {
  //     type: String,
  //     default: "Submit",
  //   },
  // },
  render(h, ctx) {
    const Prefix = "#";
    return h(
      "Button",
      {
        ...ctx.data,
        props: { ...ctx.props, label: "Submit" /** extend any props */ },
      },
      [Prefix],
      ...(ctx.children || [])
    );
  },
};
</script>

