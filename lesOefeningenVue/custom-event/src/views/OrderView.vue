<template>
  <div>
    <h3>AANGEKOCHTE ITEMS</h3>
    <table>
      <tr v-for="item in this.shoppingBasket" :key="item.id">
         <td>{{ item.omschrijving }}</td>
         <td>{{ item.prijs }} EURO</td>

      </tr>
      <tr><td>Totaal aantal: {{ shoppingBasket.length }}</td></tr>
    </table>
  </div>
  <CatalogPage @ontvangItem="receiveItem($event)"/>
</template>

<script>
import CatalogPage from "@/components/CatalogPage.vue";

export default {
  name: "OrderView",
  components: {CatalogPage},
  data() {
    return {
      selectedProduct: {},
      shoppingBasket: []
    }
  },
  methods: {
    receiveItem(itemObject) {
      this.selectedProduct = itemObject
      this.shoppingBasket.push(this.selectedProduct)
    }
  }
}
</script>

<style scoped>

</style>