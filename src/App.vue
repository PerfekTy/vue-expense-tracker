<script setup>
import HeaderC from "./components/HeaderC.vue";
import Balance from "./components/BalanceC.vue";
import IncomeExpenses from "./components/IncomeExpenses.vue";
import TransitionList from "./components/TrasactionList.vue";
import AddTrasaction from "./components/AddTransaction.vue";

import { ref, computed } from "vue";

const transactions = ref([
  { id: 1, text: "Flower", amount: -19.99 },
  { id: 2, text: "Salary", amount: 299.97 },
  { id: 3, text: "Book", amount: -10 },
  { id: 4, text: "Camera", amount: 150 },
]);

const total = computed(() =>
  transactions.value.reduce((acc, transaction) => acc + transaction.amount, 0)
);

const income = computed(() =>
  transactions.value
    .filter((transaction) => transaction.amount > 0)
    .reduce((acc, transaction) => acc + transaction.amount, 0)
    .toFixed(2)
);

const expenses = computed(() =>
  transactions.value
    .filter((transaction) => transaction.amount < 0)
    .reduce((acc, transaction) => acc + transaction.amount, 0)
    .toFixed(2)
);
</script>

<template>
  <HeaderC />
  <div class="container">
    <Balance :total="total" />
    <IncomeExpenses :income="income" :expenses="expenses" />
    <TransitionList :transactions="transactions" />
    <AddTrasaction />
  </div>
</template>
