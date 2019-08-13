<template>
  <div>
    <h1>Dashboard</h1>
    <v-data-table
      :headers="headers"
      :items="employees"
      :items-per-page="5"
      class="elevation-1"
      @click:row="selectRow"
      multi-sort="true"
    ></v-data-table>
    <v-snackbar
      v-model="snackbar"
    >
      You have selected {{ currentItem }}
      <v-btn
        color="pink"
        text
        @click="snackbar = false"
      >
        Close
      </v-btn>
    </v-snackbar>
  </div>
</template>

<script>
import employeesData from '../data/employees.json'

export default {
  name: 'DashboardPage',
  data () {
    return {
      currentItem: '',
      snackbar: false,
      headers: [
        { text: 'Employee ID', value: 'id' },
        { text: 'Name', value: 'name' },
        { text: 'Position Title', value: 'title' },
        { text: 'Salary', value: 'salary' },
      ],
      employees: employeesData
    }
  },
  methods: {
    selectRow(event) {
      this.snackbar = true
      this.currentItem = event.name
    }
  }
}
</script>

<style>

</style>
