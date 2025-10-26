<script setup lang="ts">
// import { computed } from 'vue'
import { Input } from './ui/input'

// const props = defineProps({
//   name: String,
// })
// const emit = defineEmits(['update:name'])

// const localName = computed({
//   get() {
//     return props.name
//   },
//   set(value) {
//     emit('update:name', value) // 觸發事件通知父層更新
//   },
// })

const model = defineModel<string>('name')
</script>
<template>
  <Input v-model="model" />
</template>
