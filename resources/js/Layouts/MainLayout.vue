<template>
  <header class="border-b border-gray-200 dark:border-gray-700 dark:bg-gray-900 w-full">
    <div class="container mx-auto">
      <nav class="p-4 flex items-center justify-between">
        <div class="text-lg font-medium">
          <Link :href="route('listing.index')">Listing</Link>
        </div>
        <div class="text-xl text-indigo-600 dark:text-indigo-300 font-bold text-center">
          <Link :href="route('listing.index')">LaraZillow</Link>
        </div>
        <div>
          <Link :href="route('listing.create')" class="button">+ New Listing</Link>
        </div>
      </nav>
    </div>
  </header>

  <main class="container mx-auto - p-4">
    <div v-if="flashSuccess" class=" mb-4 border rounded-md shadow-sm border-green-200 dark:border-green-800 bg-green-50 dark:bg-green-900 p-2">
      {{ flashSuccess }}
    </div>
    <slot>Default</slot>
  </main>
</template>

<script setup>
import { usePage, Link } from '@inertiajs/vue3'
import { computed } from 'vue'
import { route } from 'ziggy'

const page = usePage()

const flashSuccess = computed(
  () => page.props.flash.success,
)

</script>