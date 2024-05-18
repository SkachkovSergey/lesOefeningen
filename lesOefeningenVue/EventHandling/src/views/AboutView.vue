<template>

  <div class="about">
     <div>
       <h3 id="teller">TELLER: {{ teller }}</h3>
     </div>
     <div>
       <button :disabled="toestand" @click="increment" class="plusButton"> + </button>
       <button :disabled="toestand" @click="decrement" class="minusButton"> - </button>
     </div>
  </div>
</template>

<script>
export default {
  name: 'AboutView',
  data() {
    return {
      teller: 0,
      toestand: false
    }
  },
  methods: {
    increment() {
      this.teller++
      if(this.teller > 100) {
        this.teller = 0
        this.toestand = true
      }
    },
    decrement() {
      this.teller--
      if(this.teller < 0) {
        this.teller = 0
        this.toestand = true
      }
    }
  }
}
</script>

<style>
.about {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-end;
}
#teller {
  color: cornflowerblue;
  border-bottom: 2px solid blue;
}
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
.plusButton {
  background-color: forestgreen;
  margin: 5px;
  border: 2px solid black;
  width: 30px;
  font-size: 20px;
}
.minusButton {
  background-color: red;
  margin: 5px;
  border: 2px solid black;
  width: 30px;
  font-size: 20px;
}
</style>
