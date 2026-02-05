<!--
Create a `<hr>` in the presentation

Usage: `<Break />` / `<Break :size="2" />`
-->
<script setup lang="ts">
  const props = withDefaults(
    defineProps<{ size?: number }>(),
    { size: 1.5 },
  )
</script>

<template>
  <hr :style="`opacity: 0; margin: ${props.size}rem 0`" />
</template>
