<script setup lang="ts">
import TextInterpolation from './components/TextInterpolation.vue'
import { Button } from './components/ui/button'
import InputDemo from './components/InputDemo.vue'
import { ref } from 'vue'
const color: string = 'text-green-700'
const vModelText = ref('請輸入')
const handleEmitDemo = (data: string) => console.log(data)
</script>

<template>
  <div class="m-4">
    <h1 class="text-2xl font-bold text-green-600">Vue3 導讀</h1>
    <section class="m-3">
      <h2 class="text-xl font-bold">props</h2>
      <TextInterpolation msg="我是 props 的參數" />
    </section>
    <section class="m-3">
      <h2 class="text-xl font-bold">emits</h2>
      <TextInterpolation msg="我是 props 的參數" @update-value="handleEmitDemo" />
    </section>
    <section class="m-3">
      <h2 class="text-xl font-bold">v-bind</h2>
      <p :class="color">V-bind demo</p>
    </section>
    <section class="m-3">
      <h2 class="text-xl font-bold">v-on</h2>
      <Button @click="handleEmitDemo('v-on click demo')">v-on demo</Button>
    </section>
    <section class="m-3">
      <h2 class="text-xl font-bold">v-model: {{ vModelText }}</h2>
      <InputDemo v-model="vModelText" />
    </section>
  </div>
</template>

<style scoped></style>
