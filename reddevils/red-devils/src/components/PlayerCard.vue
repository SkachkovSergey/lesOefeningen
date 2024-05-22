<template>
<div v-for="player in players" :key="player.id">
  <img :src="'../src/assets/' + player.afbeelding" alt="Player Image" height="200px" width="150px">
  <span>{{ player.speler }}</span>
  <span>{{ player.geboortedatum }}</span>
  <span>{{ player.club.toUpperCase() }}</span>
  <label class="check">
    <input type="checkbox" v-model="player.selected"/>
    {{ player.selected ? 'selected': 'NOT selected'}}
  </label>

</div>
</template>

<script>
export default {
  name: "PlayerCard",
  props: {
    players: Array,
  },
  methods: {

  },

}
</script>

<style scoped>
div {
  width: 33%;
  color: blue;
  float: left;
  margin-top: 10px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
span {
  font-weight: bold;
  font-size: 25px;
}
.check, input[checkbox] {
  font-size: 27px;
}
</style>