<!--
Show label on right-top of the presentation

Usage: `<Label :color=""> Content </Label>`
-->
<script setup lang="ts">
  const props = withDefaults(
    defineProps<{ color?: string }>(),
    { color: "#A5A5A1" },
  )
</script>

<template>
  <p class="progfay-label" :style="`--progfay-label-color: ${props.color}`">
    <slot />
  </p>
</template>

<style>
  .progfay-label {
    position: absolute;
    top: 1rem;
    right: -3.25rem;
    transform: rotate(35deg);
    margin: 0;
    padding: 0.6rem 0.5rem 0.4rem;
    text-align: center;
    vertical-align: middle;
    font-weight: 700;
    font-size: 1.35rem;
    width: 12rem;
    background-color: var(--progfay-label-color);
  }
</style>
