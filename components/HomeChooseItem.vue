<script lang="ts" setup>
const props = defineProps({
  title: String,
});
</script>

<template>
  <slot name="icon" />

  <div class="text-zinc-800 text-base font-bold font-['Inter']">
    {{ props.title }}
  </div>

  <div class="">
    <slot name="desc"></slot>
  </div>
</template>

<style scoped></style>
