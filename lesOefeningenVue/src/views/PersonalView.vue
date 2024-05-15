<template>
  <PersonalPage :msg/>
</template>

<script>
import PersonalPage from "@/components/PersonalPage.vue"

export default {
  name: "PersonalView",
  components: {
    PersonalPage,
  },
  data() {
    return {
      msg: 'Welcome op mijn webpagina',
    }
  }
}
</script>

<style scoped>
@media (min-width: 1024px) {
  h1 {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>