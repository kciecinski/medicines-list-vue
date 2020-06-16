<template>
  <div class="tile is-vertical form-tile">
    <h2 class="title">Add New Medicine Order</h2>
    <b-field label="Medicines">
      <b-select v-model="order.medicines" placeholder="Select medicine" required expanded>
        <option value="Ibubrofen">Ibubrofen</option>
        <option value="Xanax">Xanax</option>
        <option value="Morfina">Morfina</option>
        <option value="Paracetamol">Paracetamol</option>
      </b-select>
    </b-field>
    <b-field label="Select Date an Time">
      <b-datetimepicker
          v-model="order.datetime"
          rounded
          placeholder="Click to select..."
          icon="calendar-today"
          horizontal-time-picker
          >
      </b-datetimepicker>
    </b-field>
    <b-field label="Quantity">
      <b-numberinput min="0" v-model="order.quantity"></b-numberinput>
    </b-field>
    <b-field label="Departament">
      <b-select v-model="order.departament" placeholder="Select Departament" required expanded>
        <option value="SOR">SOR</option>
        <option value="Onkologia">Onkologia</option>
        <option value="Kardiologia">Kardiologia</option>
        <option value="OIOM">OIOM</option>
      </b-select>
    </b-field>
    <h3 class="subtitle">Patient Info</h3>
    <b-field label="First Name">
        <b-input v-model="order.patient.firstName"></b-input>
    </b-field>
    <b-field label="Last Name">
      <b-input v-model="order.patient.lastName"></b-input>
    </b-field>
    <b-field label="ID">
      <b-input v-model="order.patient.id"></b-input>
    </b-field>
    <div class="buttons">
      <b-button type="is-primary" expanded @click="submitForm">Submit</b-button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'OrderForm',
  data() {
    return {
      order: {
        medicines : "",
        datetime: "",
        quantity: 0,
        departament: "",
        patient: {
          firstName: "",
          lastName: "",
          id: ""
        }
      }
    }
  },
  methods: {
    submitForm: function() {
      this.order.datetime = this.formatDate(this.order.datetime)
      this.$emit('submitForm', this.order)
      this.order = {
        medicines : "",
        datetime: "",
        quantity: 0,
        departament: "",
        patient: {
          firstName: "",
          lastName: "",
          id: ""
        }
      }
    },
    formatDate(dateString) {
      const date = new Date(dateString)
      return date.toLocaleString()
    }
  }

}
</script>

<style scped>
  .form-tile {
    margin: 35px 40px;
    padding: 0px 150px;
  }
  .buttons {
    margin-top: 15px;
  }
</style>