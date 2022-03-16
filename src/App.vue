<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router';
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/dashboard">Dashboard</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style lang="scss">
@import '@/assets/base.css';

#app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;
  font-weight: normal;
}

nav {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  margin-bottom: 2rem;

  a {
    display: inline-block;
    margin-right: 2rem;
    color: #ccc;
    text-decoration: none;
    font-size: 22px;

    &:hover {
      color: #fff;
    }
  }
}
</style>
