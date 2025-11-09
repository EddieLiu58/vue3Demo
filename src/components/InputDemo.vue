<script setup lang="ts">
import { onUpdated } from 'vue'
import { Input } from './ui/input'
const model = defineModel<string>()
onUpdated(() => {
  console.log('InputDemo updated')
  console.log(model.value)
})
</script>
<template>
  <Input v-model="model" />
</template>
