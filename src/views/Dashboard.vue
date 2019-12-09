<template>
  <v-container>
    <h1>Dashboard</h1>

    <v-row>
      <v-col v-for="sale in sales" :key="`${sale.title}`" cols="12" md="4">
        <SalesGraph :sale="sale" />
      </v-col>
    </v-row>

    <v-row>
      <v-col
        v-for="statistic in statistics"
        :key="`${statistic.title}`"
        cols="12"
        md="6"
        lg="3"
      >
        <StatisticCard :statistic="statistic" />
      </v-col>
    </v-row>

    <v-row>
      <v-col cols="12" md="8">
        <EmployeesTable :employees="employees" @select-employee="setEmployee" />
      </v-col>
      <v-col cols="12" md="4">
        <EventTimeline :timeline="timeline" />
      </v-col>
    </v-row>

    <v-row id="below-the-fold" v-intersect="showMoreContent">
      <v-col cols="12" md="8">
        <EmployeesTable :employees="employees" @select-employee="setEmployee" />
      </v-col>
      <v-col cols="12" md="4">
        <EventTimeline :timeline="timeline" />
      </v-col>
    </v-row>

    <v-row v-if="loadNewContent" id="more-content">
      <v-col>
        <v-skeleton-loader
          ref="skeleton"
          type="table"
          class="mx-auto"
        ></v-skeleton-loader>
      </v-col>
    </v-row>

    <v-snackbar v-model="snackbar" :left="$vuetify.breakpoint.lgAndUp">
      You have selected {{ selectedEmployee.name }},
      {{ selectedEmployee.title }}
      <v-btn color="pink" text @click="snackbar = false">
        Close
      </v-btn>
    </v-snackbar>
  </v-container>
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
      loadNewContent: false,
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
    },
    showMoreContent(entries) {
      this.loadNewContent = entries[0].isIntersecting
    }
  }
}
</script>
