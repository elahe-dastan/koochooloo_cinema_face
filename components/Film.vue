<template>
  <nuxt-link :to="'films/' + id">
    <div class="film">
      <p>{{ id }} - {{ name }} - {{ file }} - {{ production_year }}</p>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  props: {
    id: {},
    file: {},
    name: {},
    production_year: {}
  }
}
</script>

<style scoped>

</style>
