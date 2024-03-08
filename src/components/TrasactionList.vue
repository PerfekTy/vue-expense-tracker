<template>
  <h3>History</h3>
  <ul id="list" class="list">
    <li
      :key="transaction.id"
      :class="transaction.amount < 0 ? 'minus' : 'plus'"
      v-for="transaction in transactions"
    >
      {{ transaction.text }} <span>${{ transaction.amount }}</span>
      <button @click="deleteTransaction(transaction.id)" class="delete-btn">
        x
      </button>
    </li>
  </ul>
</template>

<script setup>
import { defineProps } from "vue";

const emit = defineEmits(["transactionDeleted"]);

defineProps({
  transactions: {
    type: Array,
    required: true,
  },
});

const deleteTransaction = (id) => {
  emit("transactionDeleted", id);
};
</script>
