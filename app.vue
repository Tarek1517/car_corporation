<template>
  <div>
    <NuxtRouteAnnouncer />
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </div>
</template>
<style>
@import "tailwindcss";
@import "@nuxt/ui";
@theme {
  --color-primary: #8b0000;
  --color-secondary: #ff0000;
}
</style>
