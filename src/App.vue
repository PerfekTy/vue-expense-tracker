<script>
import HeaderC from "./components/HeaderC.vue";
import Balance from "./components/BalanceC.vue";
import IncomeExpenses from "./components/IncomeExpenses.vue";
import TransitionList from "./components/TrasactionList.vue";
import AddTrasaction from "./components/AddTransaction.vue";

export default {
  components: {
    HeaderC,
    Balance,
    IncomeExpenses,
    TransitionList,
    AddTrasaction,
  },
};
</script>

<template>
  <HeaderC />
  <div class="container">
    <Balance />
    <IncomeExpenses />
    <TransitionList />
    <AddTrasaction />
  </div>
</template>
