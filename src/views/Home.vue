<template>
  <div class="home">
    <input
      type="text"
      v-model.trim="userInput"
      placeholder="type something..."
    />
    <ChildComponent :msg="userInput" @clearInput="clearInput()" />
  </div>
</template>

<script>
// @ is an alias to /src
import ChildComponent from "@/components/ChildComponent.vue";

export default {
  name: "Home",
  data() {
    return {
      userInput: "",
    };
  },
  components: {
    ChildComponent,
  },
  methods: {
    clearInput() {
      this.userInput = "";
    },
  },
  metaInfo: {
    title: "Home Page",
    titleTemplate: "%s - A random vue site",
    meta: [
      { name: 'description', content: 'This is A random vue site.' }
    ]
  },
};
</script>
