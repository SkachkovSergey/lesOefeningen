<template>
  <table>
    <thead>PRODUCT CATALOG OVERVIEW</thead>
    <tr><td><b>Omschrijving</b></td><td><b>Prijs</b></td><td><b>Aantal</b></td></tr>
    <tr v-for="item in catalogus">
      <td>{{ item.omschrijving }}</td>
      <td>{{ item.prijs }} EURO</td><td>
      <button @click="setItem(item)">+</button></td></tr>
  </table>
</template>

<script>
export default {
  name: "CatalogPage",
  data() {
    return {
      catalogus: [
        {id: 1, omschrijving: "Melk", prijs: 1},
        {id: 2, omschrijving: "tandpasta", prijs: 2},
        {id: 3, omschrijving: "boter", prijs: 1},
        {id: 4, omschrijving: "Honing", prijs: 1},
        {id: 5, omschrijving: "Yoghurt", prijs: 5.23},
        {id: 6, omschrijving: "Pasta", prijs: 2},
      ],
      newObject: {}
    }
  },
  methods: {
    setItem(item) {
      this.newObject = item
      this.$emit('ontvangItem', this.newObject)
    }
  }
}
</script>

<style scoped>

</style>