<template>
  <div class="container">
    <h1>{{ msg }}</h1>
    <p>{{ persoonlijk.naam }}</p>
    <p>{{ persoonlijk.adres }}</p>
    <p>{{ persoonlijk.plaats }}</p>
  </div>
</template>

<script>
export default {
  name: "PersonalPage",
  props: {
    msg: String,
  },
  data() {
    return {
      persoonlijk: {
        naam: 'Sergey Skachkov',
        adres: 'Elfde Liniestraat 24',
        plaats: '3500 Hasselt'
      }
    }
  }
}
</script>

<style scoped>
@media (min-width: 1024px) {
  .container {
    min-height: 100vh;
    display: flex;
    align-items: start;
    flex-direction: column;
  }
}
</style>