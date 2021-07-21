<template>
  <div>
  <nuxt-link to="/films">Back to films
  </nuxt-link>
  <h2>{{ film }}</h2>
    <hr />
    <small>Film ID: {{ $route.params.id }}</small>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  // name: "index"
  data(){
    return {
      film: {}
    }
  },
  async created() {
    const config = {
      headers: {
        'Accept': 'application/json'
      }
    }

    try {
      const res = await axios.get(`http://localhost:1373/api/film/${this.$route.params.id}`, config)
      console.log(res.data)
      this.film = res.data
    } catch (err) {
      console.log(err)
    }
  },
}
</script>

<style scoped>

</style>
