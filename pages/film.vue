<template>
<div>
  <film v-for="film in films" :key="film.name"
  :file="film.file" :name="film.name" :production_year="film.production_year"></film>
</div>
</template>

<script>
import axios from "axios";
import film from '../components/film';

export default {
  components: {
    film
  },

  data: () => ({
    films: {}
  }),

  async created() {
    const config = {
      headers : {
        'Accept' : 'application/json'
      }
    }

    try {
      const res = await axios.get('http://localhost:1373/api/tag?tag=a', config)
      console.log(res.data)
      this.films = res.data
    }catch (err) {
      console.log(err)
    }
  },
}
</script>

<style scoped>

</style>
