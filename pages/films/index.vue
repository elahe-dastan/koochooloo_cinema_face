<template>
  <div>
    <Film v-for="film in films" :key="film.id"
          :id="film.id" :file="film.file" :name="film.name" :production_year="film.production_year"></Film>
  </div>
</template>

<script>
import axios from "axios";
import Film from "../../components/Film";

export default {
  components: {
    Film
  },

  data: () => ({
    films: {}
  }),

  async created() {
    const config = {
      headers: {
        'Accept': 'application/json'
      }
    }

    try {
      const res = await axios.get('http://localhost:1373/api/tag?tag=a', config)
      console.log(res.data)
      this.films = res.data
    } catch (err) {
      console.log(err)
    }
  },
}
</script>

<style scoped>

</style>
