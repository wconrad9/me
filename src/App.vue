<script setup>
import Home from './views/Home.vue';
</script>

<template>
  <header>
    <div class="wrapper">
      <Home />
    </div>
  </header>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: start;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
    z-index: 1;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
