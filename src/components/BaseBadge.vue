<script setup lang="ts">
import type { Status } from '@/types/Status.ts'
import { Icon } from '@iconify/vue'

type BadgeColor = 'green' | 'yellow' | 'red'

defineProps<{
  status: Status
}>()

const stylingVariants: { [key in Status]: BadgeColor } = {
  Completed: 'green',
  Pending: 'yellow',
  Canceled: 'red'
}
</script>

<template>
  <div class="badge" :class="`badge--${stylingVariants[status]}`">
    <Icon icon="oui:dot" width="1.2em" height="1.2em" />
    <span style="font-weight: 500">
      {{ status }}
    </span>
  </div>
</template>

<style lang="scss" scoped>
.badge {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  padding-block: 4px;
  padding-inline: 12px;
  border-radius: 9999px;

  &--green {
    color: rgb(34 197 94);
    background-color: rgba(34, 197, 94, 0.2);
  }

  &--yellow {
    color: rgb(234 179 8);
    background-color: rgba(234, 179, 8, 0.2);
  }

  &--red {
    color: rgb(239 68 68);
    background-color: rgba(239, 68, 68, 0.2);
  }
}
</style>
