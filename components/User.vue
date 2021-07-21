<template>
  <form @submit.prevent="OnSubmit">
    <input type="text" v-model="text" placeholder="username">
    <input type="submit" value="submit">
  </form>
</template>

<script>
import Index from "../pages/films";
export default {
  name: "User",
  components: {Index},
  data() {
    return {
      text: ''
    }
  },
  methods: {
    OnSubmit() {
      this.$emit('username-text', this.text);
      this.text = "";
    }
  }
}
</script>

<style scoped>

</style>
