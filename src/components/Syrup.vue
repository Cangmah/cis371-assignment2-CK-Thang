<template>
  <div class="syrup"></div>
</template>

<script setup lang="ts">
import { computed } from "vue";
import type { SyrupType } from "../stores/beverage";

const props = defineProps<{ syrup: SyrupType }>();
const color = computed(() => props.syrup.color);
</script>

<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  background: repeating-linear-gradient(
    45deg,
    rgba(225, 207, 149, 1),
    rgba(225, 207, 149, 1) 10px,
    v-bind(color) 10px,
    v-bind(color) 20px
  );
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}
</style>