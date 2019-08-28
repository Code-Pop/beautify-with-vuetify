<template>
  <div>
    <h1>Dashboard</h1>

    <SalesGraph v-for="sale in sales" :key="`${sale.title}`" :sale="sale" />

    <StatisticCard
      v-for="statistic in statistics"
      :key="`${statistic.title}`"
      :statistic="statistic"
    />

    <EmployeesTable :employees="employees" @select-employee="setEmployee" />

    <EventTimeline :timeline="timeline" />

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
import EventTimeline from '../components/EventTimeline'
import SalesGraph from '../components/SalesGraph'
import StatisticCard from '../components/StatisticCard'

import employeesData from '../data/employees.json'
import timelineData from '../data/timeline.json'
import salesData from '../data/sales.json'
import statisticsData from '../data/statistics.json'

export default {
  name: 'DashboardPage',
  components: {
    EmployeesTable,
    EventTimeline,
    SalesGraph,
    StatisticCard
  },
  data() {
    return {
      employees: employeesData,
      sales: salesData,
      selectedEmployee: {
        name: '',
        title: ''
      },
      snackbar: false,
      statistics: statisticsData,
      timeline: timelineData
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
