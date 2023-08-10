<template>
  <form-input :fieldProperties="inputData"></form-input>
</template>

<script>
import FormInput from "./components/FormInput.vue";
export default {
  name: "app",
  data() {
    return {
      inputData: {
        label: "Name",
        name: "userName",
        type: "text",
        placeholder: "Enter Your Name",
      },
    };
  },
  components: {
    FormInput,
  },
};
</script>
