<template>
  <h3>History</h3>
  <ul id="list" class="list">
    <li
      :key="transaction.id"
      :class="transaction.amount < 0 ? 'minus' : 'plus'"
      v-for="transaction in transactions"
    >
      {{ transaction.text }} <span>${{ transaction.amount }}</span>
      <button class="delete-btn">x</button>
    </li>
  </ul>
</template>

<script setup>
import { defineProps } from "vue";

defineProps({
  transactions: {
    type: Array,
    required: true,
  },
});
</script>
