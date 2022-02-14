<template>
  <v-data-table
    :headers="headers"
    :items="employees"
    :items-per-page="5"
    class="elevation-1"
    @click:row="selectRow"
    :multi-sort="true"
  ></v-data-table>
</template>

<script>
export default {
  name: 'EmployeesTable',
  props: {
    employees: {
      type: Array,
      required: true
    }
  },
  data: () => ({
    headers: [
      { text: 'Nhóm ngành', value: 'id' },
      { text: 'Tên mã', value: 'name' },
      { text: 'Tên công ty', value: 'title' },
      { text: 'Mức giá', value: 'salary' }
    ]
  }),
  methods: {
    selectRow(event) {
      const employee = {
        name: event.name,
        title: event.title
      }

      this.$emit('select-employee', employee)
    }
  }
}
</script>

<style lang="scss" scoped></style>
