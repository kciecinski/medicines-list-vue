<template>
  <div class="tile is-vertical form-tile">
    <h2 class="title">Add New Medicine Order</h2>
    <b-field label="Medicines">
      <b-select v-model="medicines" placeholder="Select medicine" required expanded>
        <option value="Ibubrofen">Ibubrofen</option>
        <option value="Xanax">Xanax</option>
        <option value="Morfina">Morfina</option>
        <option value="Paracetamol">Paracetamol</option>
      </b-select>
    </b-field>
    <b-field label="Select Date an Time">
      <b-datetimepicker
          v-model="datetime"
          rounded
          placeholder="Click to select..."
          icon="calendar-today"
          horizontal-time-picker>
      </b-datetimepicker>
    </b-field>
    <b-field label="Quantity">
      <b-numberinput min="0" v-model="quantity"></b-numberinput>
    </b-field>
    <b-field label="Departament">
      <b-select v-model="departament" placeholder="Select Departament" required expanded>
        <option value="SOR">SOR</option>
        <option value="Onkologia">Onkologia</option>
        <option value="Kardiologia">Kardiologia</option>
        <option value="OIOM">OIOM</option>
      </b-select>
    </b-field>
    <h3 class="subtitle">Patient Info</h3>
    <b-field label="First Name">
        <b-input v-model="patient.firstName"></b-input>
    </b-field>
    <b-field label="Last Name">
      <b-input v-model="patient.lastName"></b-input>
    </b-field>
    <b-field label="ID">
      <b-input v-model="patient.id"></b-input>
    </b-field>
    <div class="buttons">
      <b-button type="is-primary" expanded>Submit</b-button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'OrderForm',
  data() {
    return {
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