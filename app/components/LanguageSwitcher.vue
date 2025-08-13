<script setup lang="ts">
const { locale, locales, setLocale } = useI18n()

const localeOptions = computed(() => locales.value.map((i) => ({
  label: i.name,
  value: i.code,
})))

const currentLocale = computed({
  get: () => locale.value,
  set: (value) => setLocale(value),
});
</script>

<template>
  <USelect v-model="currentLocale" :items="localeOptions" class="w-48" />
</template>