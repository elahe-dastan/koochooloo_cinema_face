<template>
  <div>
    <Signup v-on:signup="signup"></Signup>
  </div>
</template>

<script>
import Signup from "../components/Signup";
import axios from "axios";

export default {
  name: "signup",
  components: {
    Signup
  },
  methods: {
    async signup(username, password,first_name,last_name,email,phone, national_number) {
      await axios.post(`http://localhost:1373/api/signup`, {
        username: username,
        password: password,
        first_name: first_name,
        last_name: last_name,
        email: email,
        phone: phone,
        national_number: national_number
      })
        .then(function (response) {
          console.log(response);
        })
        .catch(function (error) {
          console.log(error)
        })
    }
  },
}
</script>

<style scoped>

</style>
