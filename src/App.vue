<template>
  <header>
    <div class="wrapper text-center">
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <!-- <RouterLink to="/sign-up">About</RouterLink> -->
      </nav>
    </div>
  </header>

  <RouterView />
</template>

  <script setup>
  import { RouterLink, RouterView } from 'vue-router'
  </script>
