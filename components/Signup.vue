<template>
  <v-form  @submit.prevent="OnSubmit">
    <v-container>
      <v-row>
        <v-col
          cols="12"
          md="4"
        >
          <v-text-field v-model="username" label="Username"></v-text-field>
        </v-col>
        <v-col
          cols="12"
          md="4"
        >
          <v-text-field v-model="password" label="Password"></v-text-field>
        </v-col>
        <v-col
          cols="12"
          md="4"
        >
          <v-text-field v-model="email" label="Email"></v-text-field>
        </v-col>
      </v-row>
      <v-row>
        <v-col
          cols="12"
          md="4"
        >
          <v-text-field v-model="first_name" label="First Name"></v-text-field>
        </v-col>
        <v-col
          cols="12"
          md="4"
        >
          <v-text-field v-model="last_name" label="Last Name"></v-text-field>
        </v-col>
        <v-col
          cols="12"
          md="4"
        >
          <v-text-field v-model="phone" label="Phone"></v-text-field>
        </v-col>
        <v-col
          cols="12"
          md="4"
        >
          <v-text-field v-model="national_number" label="National Code" :counter=10></v-text-field>
        </v-col>
      </v-row>
      <v-row>
        <v-col
          cols="12"
          md="4"
        >
          <v-btn
            color="success"
            type="submit"
          >
            Submit
          </v-btn>
        </v-col>
      </v-row>
    </v-container>
  </v-form>
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
