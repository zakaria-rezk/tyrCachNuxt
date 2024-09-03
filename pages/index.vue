<script setup>
const nuxtApp = useNuxtApp();

const { data } = await useFetch("https://icanhazdadjoke.com/", {
  headers: {
    Accept: "application/json",
  },
  getCachedData(key) {
   
    return nuxtApp.payload.data[key] || nuxtApp.static.data[key];
  },
});
</script>

<template>
  <div>
    <h1>Index page</h1>
    <p>{{ data.joke }}</p>
    <NuxtLink to="/about">To the about page</NuxtLink>
  </div>
</template>
