<template>
  <div>
    <h1 class="title">List of medicines orders</h1>
    <b-table :data="data" :columns="columns" class="main-table" striped narrowed></b-table>
  </div>
</template>

<script>
export default {
  name: 'OrdersList',
  props: {
    orders: Array
  },
  data() {
    return {
      data: this.orders,
      columns: [
        {
            field: 'medicines',
            label: 'Medicines',
            width: '40',
            numeric: true
        },
        {
            field: 'datetime',
            label: 'Date and Time',
        },
        {
            field: 'quantity',
            label: 'Quantity',
        },
        {
            field: 'departament',
            label: 'Departament',
        }, 
        {
            field: 'patient.firstName',
            label: 'Patient First Name',
        },
        {
            field: 'patient.lastName',
            label: 'Patient Last Name',
        },
        {
            field: 'patient.id',
            label: 'Patient ID',
        },
      ]
    }
  }
}
</script>

<style scoped>
  .main-table {
    margin-bottom: 50px;
  }
</style>