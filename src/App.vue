<script setup>
import { defineAsyncComponent } from 'vue';
import splashscreen from '@/components/SplashScreen.vue'


const Home = defineAsyncComponent(() =>
  new Promise((resolve) => {
    setTimeout(() => {
      resolve(import("@/components/Home.vue"));
    }, 2500);
  })
)

</script>

<template>

  <Suspense>
    <template #default>
      <Home />
    </template>
    <template #fallback>
      <splashscreen />
    </template>
  </Suspense>

</template>

<style>
html,
body,
.app {
  min-height: 100vh;
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}

* {
  --brand-green: #04b500;
  --brand-blue: #0689b0;
}
</style>
