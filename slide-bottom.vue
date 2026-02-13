<template>
  <footer
    v-if="$nav.currentLayout !== 'cover' &&
          $nav.currentLayout !== 'self-intro' &&
          $nav.currentPage > 1"
    style="position: absolute; bottom: 0; right: 0; margin: 1rem; font-size: 1rem; color: var(--progfay-note);"
  >
    {{ $nav.currentPage }}
  </footer>
</template>
