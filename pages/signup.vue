<template>
  <div>
    <User v-on:username-text="usernameText"></User>
  </div>
</template>

<script>
import User from "../components/User";
import axios from "axios";

export default {
  name: "signup",
  components: {
    User
  },
  methods: {
    async usernameText(text) {
      await axios.post(`http://localhost:1373/api/signup`, {
        username: text
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
