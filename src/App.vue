<script setup lang="ts">
import { Icon } from '@iconify/vue'
import BaseTable from './components/BaseTable.vue'
import BaseBadge from './components/BaseBadge.vue'

const columns = [
  { id: 'status', label: 'Status' },
  { id: 'type', label: 'Type' },
  { id: 'price', label: 'Price' },
  { id: 'vendor', label: 'Vendor' },
  { id: 'icon' }
]

const rows = [
  {
    status: 'Completed',
    type: 'Card payment',
    typeInfo: 'Visa card **** 4831',
    price: '$182.94',
    date: 'Jan 17, 2024',
    vendor: 'Amazon'
  },
  {
    status: 'Completed',
    type: 'Card payment',
    typeInfo: 'Mastercard **** 6642',
    price: '$99.00',
    date: 'Jan 17, 2024',
    vendor: 'Facebook'
  },
  {
    status: 'Pending',
    type: 'Bank payment',
    typeInfo: 'Account ****882',
    price: '$249.89',
    date: 'Jan 16, 2024',
    vendor: 'Netflix'
  },
  {
    status: 'Canceled',
    type: 'Card payment',
    typeInfo: 'Amex card **** 5666',
    price: '$10.99',
    date: 'Jan 16, 2024',
    vendor: 'Amazon Prime'
  }
]
</script>

<template>
  <main>
    <div class="card">
      <div class="header">
        <div>
          <h2>Transactions</h2>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
        </div>
        <button class="btn">
          <span>See All Transactions</span>
          <Icon
            icon="material-symbols:chevron-right"
            width="1.4em"
            height="1.4em"
            color="#4F46E5"
          />
        </button>
      </div>
      <BaseTable :rows="rows" :columns="columns">
        <template #status="{ row }">
          <BaseBadge :status="row.status" />
        </template>
        <template #type="{ row }">
          <span style="display: block; font-weight: bold">{{ row.typeInfo }}</span>
          <span>{{ row.type }}</span>
        </template>
        <template #price="{ row }">
          <span style="display: block; font-weight: bold">{{ row.price }}</span>
          <span>{{ row.date }}</span>
        </template>
        <template #icon>
          <Icon icon="fluent:more-horizontal-28-filled" width="1.2em" height="1.2em" />
        </template>
      </BaseTable>
    </div>
  </main>
</template>

<style lang="scss" scoped>
main {
  min-height: 100vh;
  background-color: #fee2e2;
  display: flex;
  justify-content: center;
  align-items: center;
}

.card {
  display: flex;
  flex-direction: column;
  background-color: white;
  max-width: 1024px;
  width: 100%;
  overflow-x: auto;
  border-radius: 8px;
  //padding: 28px;
  box-shadow:
    0 1px 3px 0 rgb(0 0 0 / 0.1),
    0 1px 2px -1px rgb(0 0 0 / 0.1);
}

.header {
  display: flex;
  justify-content: space-between;
  padding: 32px;

  h2 {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 0.25rem;
  }

  p {
    font-weight: 300;
  }

  button {
    display: flex;
    color: #4f46e5;
    font-size: 16px;
    border: none;
    background-color: white;
    cursor: pointer;
  }
}
</style>
