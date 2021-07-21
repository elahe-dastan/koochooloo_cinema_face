<template>
  <form @submit.prevent="OnSubmit">
    <input type="text" v-model="username" placeholder="username">
    <input type="text" v-model="password" placeholder="password">
    <input type="text" v-model="first_name" placeholder="first name">
    <input type="text" v-model="last_name" placeholder="last name">
    <input type="text" v-model="email" placeholder="email">
    <input type="text" v-model="phone" placeholder="phone">
    <input type="text" v-model="national_number" placeholder="national number">
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
      username: '',
      password: '',
      first_name: '',
      last_name: '',
      email: '',
      phone: '',
      national_number: ''
    }
  },
  methods: {
    OnSubmit() {
      this.$emit('signup', this.username, this.password, this.first_name, this.last_name, this.email, this.phone,
      this.national_number);
      this.username = "";
    }
  }
}
</script>

<style scoped>

</style>
