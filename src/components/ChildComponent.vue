<template>
  <div class="child">
    <h1>The data from parent:</h1>
    <h1 v-if="msg" class="input-text">{{ msg }}</h1>
    <h1 v-else class="input-text">waiting for input...</h1>
    <p>The button below is in a child component,</p>
    <p>
      click it to a method in parent component, which will clear the user input.
    </p>
    <a class="btn effect" @click.prevent="$emit('clearInput')" data-sm-link-text="CLEAR"><span>Clear Input</span></a>
  </div>
</template>

<script>
export default {
  name: "ChildComponent",
  props: {
    msg: String,
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/master";

.input-text {
  color: $secondary;
}

</style>