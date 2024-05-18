<template>
  <div class="container">
    <h3>{{ title }}</h3>
    <ul>
      <li v-for="(hobby, index) in hobbies"
          :key="hobby.id"
          @mouseover="toonClub(index)"
      @click="selectHobby(index)">{{ index + ' - ' + hobby.naam }}</li>
    </ul>
    <p>Club: {{ hobbies[hoveredClub].club }}</p>
    <h3>Uitgebreide info</h3>
<!--    <p>{{ hobbies[selectHobbyIndex].id + ' - ' + hobbies[selectHobbyIndex].naam + ' - '-->
<!--    + hobbies[selectHobbyIndex].club + ' - ' + hobbies[selectHobbyIndex].plaats }}</p>-->
    <p v-if="zichtbaar">{{ selectedHobbyIndex.id }} - {{ selectedHobbyIndex.naam}} -
       {{ selectedHobbyIndex.club }} - {{ selectedHobbyIndex.plaats }}</p>
    <img v-if="isZichtbaar" :src="this.selectedHobbyIndex.afbeelding" alt="photo"
         height="100px">

  </div>
</template>

<script>
export default {
  name: "HobbyView",
  data() {
    return {
      hobbies: [
        {id: 1, naam: 'Voetbal', club: 'RSCA', plaats: '1000 Brussel', afbeelding: '../src/assets/voetbal.png'},
        {id: 2, naam: 'Golf', club: 'Spiegelven Golf Club', plaats: '3600 Genk', afbeelding: '../src/assets/golf.png'},
        {id: 3, naam: 'Darts', club: 'Darts Hasselt', plaats: '3500 Hasselt', afbeelding: '../src/assets/darts.png'},
        {id: 4, naam: 'Tennis', club: 'Lima Tennis & Padel', plaats: '3630 Eisden', afbeelding: '../src/assets/tennis.png'},
        {id: 5, naam: 'Basketbal', club: 'Club Maaseik VZM', plaats: '3680 Maaseik', afbeelding: '../src/assets/basketbal.png'},
        {id: 6, naam: 'Volleybal', club: 'Green Yard', plaats: '3500 Hasselt', afbeelding: '../src/assets/volleybal.png'},
      ],
      title: 'Mijn hobbies',
      hoveredClub: 0,
      selectHobbyIndex: 0,
      zichtbaar: false,
    }
  },
  methods: {
    toonClub(index) {
      this.hoveredClub = index
    },
    selectHobby(index) {
      this.selectHobbyIndex = index
      this.zichtbaar = true
    }
  },
  computed: {
    selectedHobbyIndex() {
      return this.hobbies[this.selectHobbyIndex]
    },
    isZichtbaar() {
      return this.zichtbaar
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
h3 {
  color: blue;
  font-size: 24px;
}
</style>