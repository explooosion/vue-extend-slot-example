<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <div class="row">
      <div>Button With Default Slot</div>
      <Button label="Submit" @click="onClick">#</Button>
    </div>
    <div class="row">
      <div>Button With After Slot</div>
      <Button label="Submit" @click="onClick">
        <template #after>@</template>
      </Button>
    </div>
    <div class="row">
      <div>Button Extend A Template</div>
      <ResetButton @click="onClick" />
    </div>
    <div class="row">
      <div>Button Extend By Functional</div>
      <SubmitButton @click="onClick" />
    </div>
  </div>
</template>

<script>
import Button from "./components/Button";
import SubmitButton from "./components/SubmitButton";
import ResetButton from "./components/ResetButton";

export default {
  name: "App",
  components: {
    Button,
    SubmitButton,
    ResetButton,
  },
  methods: {
    onClick() {
      console.log("onClick");
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  text-align: center;
  margin: 60px auto 0;
}
.row {
  margin-top: 2rem;
}
</style>
