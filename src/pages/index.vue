<script setup lang="ts">
import { ref } from 'vue'
import { useFetch } from '@vueuse/core'
const users = ref([])
const { data } = await useFetch(
  'https://jsonplaceholder.typicode.com/users',
)
  .get()
  .json()
users.value = data.value
</script>

<template>
  <div>
    {{ users }}
  </div>
</template>
