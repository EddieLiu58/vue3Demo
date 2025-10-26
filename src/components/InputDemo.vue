<script setup lang="ts">
import { Input } from './ui/input'
const model = defineModel()
</script>
<template>
  <Input v-model="model" />
</template>
