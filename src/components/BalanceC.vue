<template>
  <h4>Your Balance</h4>
  <div id="balance">${{ total }}</div>
</template>

<script setup>
import { defineProps } from "vue";

defineProps({
  total: {
    type: Number,
    required: true,
  },
});
</script>
