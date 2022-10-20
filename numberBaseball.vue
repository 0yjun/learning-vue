<template>
  <div>{{ result }}</div>
  <form v-on:submit="onSubmitForm"></form>
</template>

<script>
export default {
  data() {
    return {
      value: "",
      result: "",
    };
  },
  methods: {},
};
</script>

<style></style>
