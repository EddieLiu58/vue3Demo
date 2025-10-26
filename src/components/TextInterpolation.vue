<script setup lang="ts">
import { ref } from 'vue'
import Button from './ui/button/Button.vue'

const props = defineProps({ msg: String })

const count = ref(0)

const handleClick = () => {
  count.value++
  emit('updateValue', `從子元件傳變數到父元件 ${count.value}`)
}

const emit = defineEmits<{
  updateValue: [value: string]
}>()
</script>

<template>
  <span class="text-gray-600">Message: {{ props.msg }}</span>
  <Button @click="handleClick" class="ml-2">觸發 emits</Button>
</template>
