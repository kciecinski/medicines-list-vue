<template>
  <div id="app">
    <div class="container">
      <orders-list :orders="orders"/>
      <order-form />
    </div>
  </div>
</template>

<script>
import OrdersList from './components/OrdersList.vue'
import OrderForm from './components/OrderForm.vue'

export default {
  name: 'App',
  components: {
    OrdersList,
    OrderForm
  },
  data() {
    return{ 
      orders: [{
        medicines : "Ibuprofen",
        datetime: "12.04.2012",
        quantity: 12,
        departament: "SOR",
        patient: {
          firstName: "Andrew",
          lastName: "Gołota",
          id: "97021292322"
        }
      },
      {
        medicines : "Stoperan",
        datetime: "12.04.2012",
        quantity: 12,
        departament: "Onkologia",
        patient: {
          firstName: "John",
          lastName: "Malkovitch",
          id: "67021292322"
        }
      },
      {
        medicines : "Visatex",
        datetime: "12.04.2012",
        quantity: 12,
        departament: "Główny",
        patient: {
          firstName: "Sam",
          lastName: "Gammge",
          id: "87021292322"
        }
      }
    ]}
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
