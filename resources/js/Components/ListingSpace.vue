<template>
  <div>
    <span class="font-bold "> {{ listing.beds }} bds <span class="text-gray-400"> |  </span> </span>
    <span class="font-bold "> {{ listing.baths }} ba <span class="text-gray-400"> |  </span> {{ listing.area }} m² </span>
  </div>
</template>

<script setup>
defineProps({
  listing: {
    type: Object,
    required: true,
  },
})
</script>
