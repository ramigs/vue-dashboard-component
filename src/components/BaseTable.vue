<script setup lang="ts">
interface Column {
  id: string
  label?: string
}

defineProps<{
  rows: Array<{ [key: string]: any }> // equivalent to Record<string, any>
  columns: Array<Column>
}>()
</script>

<template>
  <div class="table-container">
    <table>
      <tbody>
        <tr v-for="row in rows" :key="row.toString()">
          <td v-for="column in columns" :key="column.toString()">
            <slot :name="column.id" :row="row">
              {{ row[column.id] }}
            </slot>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style lang="scss" scoped>
.table-container {
  width: 100%;
  overflow-x: auto;
}

table {
  min-width: 100%;
}

td {
  font-weight: 300;
  white-space: nowrap;
  padding-inline: 24px;
  padding-block: 16px;

  &:first-of-type {
    padding-left: 0;
  }

  &:last-of-type {
    padding-right: 0;
  }
}
</style>
