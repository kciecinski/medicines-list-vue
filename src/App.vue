<template>
  <div id="app">
    <div class="container">
      <orders-list :orders="orders"/>
      <order-form @submitForm="updateOrders"/>
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
        datetime: "6/16/2020, 5:02:00 AM",
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
        datetime: "6/14/2020, 12:02:00 AM",
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
        datetime: "3/12/2020, 1:02:00 AM",
        quantity: 12,
        departament: "Główny",
        patient: {
          firstName: "Sam",
          lastName: "Gammge",
          id: "87021292322"
        }
      }
    ]}
  },
  methods: {
    updateOrders(order) {
      this.orders.push(order)
    }
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
