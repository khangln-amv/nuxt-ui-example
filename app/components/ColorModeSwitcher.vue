<script setup lang="ts">
const colorMode = useColorMode()

const isDark = computed({
  get: () => colorMode.value === 'dark',
  set: (_isDark: string) => {
    colorMode.preference = _isDark ? 'dark' : 'light'
  }
})

const icon = computed(() => isDark.value ? 'i-lucide-moon' : 'i-lucide-sun')
</script>

<template>
  <ClientOnly v-if="!colorMode?.forced">
    <UButton
        :icon="icon"
        color="neutral"
        variant="ghost"
        @click="isDark = !isDark"
    />

    <template #fallback>
      <div class="size-8" />
    </template>
  </ClientOnly>
</template>