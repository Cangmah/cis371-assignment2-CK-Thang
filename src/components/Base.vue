<template>
  <div class="baseBeverage"></div>
</template>

<script setup lang="ts">
import { computed } from "vue";
import type { BaseBeverageType } from "../stores/beverage";

const props = defineProps<{ base: BaseBeverageType }>();
const color = computed(() => props.base.color);
</script>

<style scoped>
.baseBeverage {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  background-color: v-bind(color);
}
</style>