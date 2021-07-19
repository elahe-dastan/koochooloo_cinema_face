<template>
<div class="film">
  <p>{{ name }} - {{ file }} - {{ production_year }}</p>
</div>
</template>

<script>
export default {
  props: {
    file: {},
    name: {},
    production_year: {}
  }
}
</script>

<style scoped>

</style>
