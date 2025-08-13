<script setup lang="ts">
const { locale, locales, setLocale } = useI18n()

const localeCodes = computed(() => locales.value.map((i) => i.code))

const currentLocale = computed({
  get: () => locale.value,
  set: (value) => setLocale(value),
});
</script>

<template>
  <USelect v-model="currentLocale" :items="localeCodes" class="w-48" />
</template>