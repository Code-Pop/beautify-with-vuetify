<template>
  <div>
    <h1>Dashboard</h1>

    <EmployeesTable
      :employeesList="employeesList"
      @select-employee="setEmployee"
    />

    <v-snackbar v-model="snackbar">
      You have selected {{ selectedEmployee.name }},
      {{ selectedEmployee.title }}
      <v-btn color="pink" text @click="snackbar = false">
        Close
      </v-btn>
    </v-snackbar>
  </div>
</template>

<script>
import EmployeesTable from '../components/EmployeesTable'
import employeesData from '../data/employees.json'

export default {
  name: 'DashboardPage',
  components: {
    EmployeesTable
  },
  data() {
    return {
      employeesList: employeesData,
      selectedEmployee: {
        name: '',
        title: ''
      },
      snackbar: false
    }
  },
  methods: {
    setEmployee(event) {
      this.snackbar = true
      this.selectedEmployee.name = event.name
      this.selectedEmployee.title = event.title
    }
  }
}
</script>
