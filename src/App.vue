<script setup lang="ts">
import { Icon } from '@iconify/vue'
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
  padding: 28px;
  box-shadow:
    0 1px 3px 0 rgb(0 0 0 / 0.1),
    0 1px 2px -1px rgb(0 0 0 / 0.1);
}

.header {
  display: flex;
  justify-content: space-between;
  margin-bottom: 32px;

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
