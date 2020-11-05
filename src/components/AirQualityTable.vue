<template>
  <table>
    <thead>
      <tr>
        <th v-for="column in columns" :key="column">{{ column.label }}</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="{ fields, recordid } in dataSet" :key="recordid">
        <td v-for="column in columns" :key="column">
          <span>{{
            column.field === "measurements_lastupdated"
              ? parseDate(fields[column.field])
              : fields[column.field]
          }}</span>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: "AirQualityTable",
  props: {
    dataSet: {
      type: Object,
      default: () => {},
    },
    columns: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    parseDate(isoString) {
      return new Date(isoString).toLocaleString();
    },
  },
};
</script>
<style scoped>
table {
  width: 100%;
}
th {
  background: #908b6d;
  font-weight: 500;
  padding: 10px;
}
td {
  font-size: 14px;
  padding: 4px;
}
th:first-child {
  text-align: left;
}
td + td:not(:last-child) {
  text-align: center;
}
th:last-child,
td:last-child {
  text-align: right;
}
</style>
