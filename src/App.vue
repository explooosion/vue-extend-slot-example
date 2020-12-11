<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <h3>Extend Vue component with values for props and slots</h3>

    <!-- Common Component -->
    <hr />
    <div class="row">
      <div>Button with props</div>
      <Button label="Button" />
    </div>
    <div class="row">
      <div>Button with props and default slot</div>
      <Button label="Submit" type="submit" :bold="true">#</Button>
    </div>
    <div class="row">
      <div>Button with props and slot name #after</div>
      <Button label="Reset" type="reset" :bold="true">
        <template #after>@</template>
      </Button>
    </div>

    <!-- Template Component -->
    <hr />
    <div class="row">
      <div>Button extend a template</div>
      <ButtonTemplate @greet="onGreet" />
    </div>
    <div class="row">
      <div>Button extend a template with custom props</div>
      <ButtonTemplate
        label="New Reset"
        type="reset"
        :bold="true"
        @greet="onGreet"
      />
    </div>
    <div class="row">
      <div>Button extend a template with custom slots</div>
      <ButtonTemplate @greet="onGreet">
        <template><i class="fas fa-sync-alt"></i></template>
        <template #after><i class="fas fa-sync-alt"></i></template>
      </ButtonTemplate>
    </div>

    <!-- Functional Component -->
    <hr />
    <div class="row">
      <div>Button extend by functional</div>
      <ButtonFunctional @greet="onGreet" />
    </div>
    <div class="row">
      <div>Button extend by functional with custom props</div>
      <ButtonFunctional
        label="New Search"
        type="button"
        :bold="true"
        @greet="onGreet"
      />
    </div>
    <div class="row">
      <div>Button extend by functional with custom slots</div>
      <ButtonFunctional @greet="onGreet">
        <template><i class="fas fa-search-plus"></i></template>
        <template #after><i class="fas fa-search-plus"></i></template>
      </ButtonFunctional>
    </div>
    <hr />
  </div>
</template>

<script>
import Button from "./components/Button";
import ButtonTemplate from "./components/ButtonTemplate";
import ButtonFunctional from "./components/ButtonFunctional";

export default {
  name: "App",
  components: {
    Button,
    ButtonTemplate,
    ButtonFunctional,
  },
  methods: {
    onGreet(args) {
      console.log(args);
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
  margin: 3rem auto 0;
}
.row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 0.5rem auto;
  width: 500px;
}
</style>
