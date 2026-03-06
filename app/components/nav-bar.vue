<script setup lang="ts">
import type { TabsItem } from '@nuxt/ui'

const route = useRoute()
const router = useRouter()

const items: TabsItem[] = [
  {
    label: 'Home',
    icon: 'i-lucide-home',
    value: ''
  },
  {
    label: 'Workout',
    icon: 'i-lucide-dumbbell',
    value: 'workout'
  },
  {
    label: 'Profile',
    icon: 'i-lucide-user',
    value: 'profile'
  }
]

const active = computed({
  get() {
    if (route.path === '/') {
      return ''
    }

    return route.path.replace(/^\//, '')
  },
  set(tab) {
    router.push(tab ? `/${tab}` : '/')
  }
})
</script>

<template>
  <UTabs size="lg" v-model="active" :content="false" :items="items" class="w-full p-3 fixed bottom-0 left-0" />
</template>

