<script setup lang="ts">
import { onBeforeMount, onMounted, onUpdated } from 'vue'
import { Input } from './ui/input'
console.log('🟢 Child: setup')
const model = defineModel<string>()
onBeforeMount(() => {
  console.log('🟢 Child: onBeforeMount')
})
onMounted(() => {
  console.log('🟢 Child: InputDemo onMounted (我先好了！)')
})
onUpdated(() => {
  console.log('InputDemo updated')
  console.log(model.value)
})
</script>
<template>
  <Input v-model="model" />
</template>
