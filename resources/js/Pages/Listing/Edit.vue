<template>
  <form @submit.prevent="update">
    <div>
      <div>
        <label>Beds</label>
        <input v-model.number="form.beds" type="text" />
        <div v-if="form.errors.beds" class="error">{{ form.errors.beds }}</div>
      </div>
    </div>

    <div>
      <div>
        <label>Baths</label>
        <input v-model.number="form.baths" type="text" />
        <div v-if="form.errors.baths" class="error">{{ form.errors.baths }}</div>
      </div>
    </div>

    <div>
      <div>
        <label>Area</label>
        <input v-model.number="form.area" type="text" />
        <div v-if="form.errors.area" class="error">{{ form.errors.area }}</div>
      </div>
    </div>

    <div>
      <div>
        <label>City</label>
        <input v-model="form.city" type="text" />
        <div v-if="form.errors.city" class="error">{{ form.errors.city }}</div>
      </div>
    </div>

    <div>
      <div>
        <label>Post Code</label>
        <input v-model="form.code" type="text" />
        <div v-if="form.errors.code" class="error">{{ form.errors.code }}</div>
      </div>
    </div>

    <div>
      <div>
        <label>Street</label>
        <input v-model="form.street" type="text" />
        <div v-if="form.errors.street" class="error">{{ form.errors.street }}</div>
      </div>
    </div>

    <div>
      <div>
        <label>Street Nr</label>
        <input v-model.number="form.street_nr" type="text" />
        <div v-if="form.errors.street_nr" class="error">{{ form.errors.street_nr }}</div>
      </div>
    </div>

    <div>
      <div>
        <label>Price</label>
        <input v-model.number="form.price" type="text" />
        <div v-if="form.errors.price" class="error">{{ form.errors.price }}</div>
      </div>
    </div>

    <div>
      <button type="submit">Edit</button>
    </div>
  </form>
</template>

<script setup>
import { useForm } from '@inertiajs/vue3'
import {route} from 'ziggy'
const props = defineProps({
  listing: Object,
})

const form = useForm({
  beds: props.listing.beds,
  baths: props.listing.baths,
  area: props.listing.area,
  city: props.listing.city,
  code: props.listing.code,
  street: props.listing.street,
  street_nr: props.listing.street_nr,
  price: props.listing.price,
})

const update = () => form.put(route('listing.edit', { listing: props.listing.id }))

</script>

<style scoped>
label {
    margin-right: 2em;
}

div {
    padding: 2px;
}

.error {
    background-color: red;
    color: white;
}
</style>