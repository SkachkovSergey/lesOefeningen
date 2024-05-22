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
    <table>
      <tr><td>Id:</td><td><input type="text" v-model="newId" :disabled="true"></td></tr>
      <tr><td>Naam: </td><td><input type="text" v-model="newName"></td></tr>
      <tr><td>Club: </td><td><input type="text" v-model="newClub"></td></tr>
      <tr><td>Plaats: </td><td><input type="text" v-model="newPlace"></td></tr>
      <tr><td>Afbeelding: </td><td><input type="text" v-model="newAfbeelding"></td></tr>
      <tr><td> </td><td><button @click="addRecord">Voeg toe</button></td></tr>
    </table>
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
      newId: 0,
      newName: "",
      newClub: "",
      newPlace: "",
      newAfbeelding: "",
    }
  },
  methods: {
    toonClub(index) {
      this.hoveredClub = index
    },
    selectHobby(index) {
      this.selectHobbyIndex = index
      this.zichtbaar = true
    },
    addRecord() {
      this.hobbies.push({
        id: this.hobbies.length + 1,
        naam: this.newName,
        club: this.newClub,
        plaats: this.newPlace,
        afbeelding: "../src/assets/" + this.newAfbeelding
      })
    },
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
    align-items: center;
    flex-direction: column;
    justify-content: center;
    height: 100vh;
  }
}
h3 {
  color: blue;
  font-size: 24px;
}
</style>