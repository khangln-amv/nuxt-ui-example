<script setup lang="ts">
const { uiLocale } = useUiLocale()
</script>

<template>
  <UApp :locale="uiLocale">
    <NuxtPage />
  </UApp>
</template>