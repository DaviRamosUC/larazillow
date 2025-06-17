<template>
  <div><Link href="/">Main Page</Link></div>
  <div><Link href="/hello">Show Page</Link></div>
  <slot>Page: </slot>
</template>

<script setup>
import {Link} from '@inertiajs/vue3'
</script>