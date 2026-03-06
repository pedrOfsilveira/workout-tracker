<script setup lang="ts">
const route = useRoute()

const routeTitleMap: Record<string, string> = {
  '/': 'Home',
  '/workout': 'Workout',
  '/profile': 'Profile'
}

const routeName = computed(() => routeTitleMap[route.path] || '')
</script>

<template>
  <UApp>
    <UHeader :title="routeName" :toggle="false" />
    <UMain>
      <NuxtLayout>
        <NuxtPage />
      </NuxtLayout>
    </UMain>
  </UApp>
</template>
