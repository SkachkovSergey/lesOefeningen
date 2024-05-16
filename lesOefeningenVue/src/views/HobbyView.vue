<template>
  <div class="container">
    <h1>{{ title }}</h1>
    <ul>
      <li v-for="(hobby, index) in hobbies" :key="hobby.id" @mouseover="toonClub(index)">{{ index + ' - ' + hobby.naam }}</li>
    </ul>
    <p>Club: {{ hobbies[hoveredClub].club }}</p>
  </div>
</template>

<script>
export default {
  name: "HobbyView",
  data() {
    return {
      hobbies: [
        {id: 1, naam: 'Voetbal', club: 'RSCA', plaats: '1000 Brussel'},
        {id: 2, naam: 'Golf', club: 'Spiegelven Golf Club', plaats: '3600 Genk'},
        {id: 3, naam: 'Darts', club: 'Darts Hasselt', plaats: '3500 Hasselt'},
        {id: 4, naam: 'Tennis', club: 'Lima Tennis & Padel', plaats: '3630 Eisden'},
        {id: 5, naam: 'Basketbal', club: 'Club Maaseik VZM', plaats: '3680 Maaseik'},
        {id: 6, naam: 'Volleybal', club: 'Green Yard', plaats: '3500 Hasselt'},
      ],
      title: 'Mijn hobbies',
      hoveredClub: 0,
    }
  },
  methods: {
    toonClub(index) {
      this.hoveredClub = index
    }
  }
}
</script>

<style scoped>
@media (min-width: 1024px) {
  .container {
    min-height: 10vh;
    display: flex;
    align-items: start;
    flex-direction: column;
  }
}
</style>