<script setup lang="ts">
import TextInterpolation from '../components/TextInterpolation.vue'
import { Button } from '../components/ui/button'
import InputDemo from '../components/InputDemo.vue'
import InputDemo2 from '../components/InputDemo2.vue'
import { onBeforeUnmount, onMounted, onUpdated, reactive, readonly, ref, watch } from 'vue'
const color: string = 'text-green-700'
const vModelText = ref('請輸入')
const demoDefaultForm = reactive({
  name: 'Eddie',
})
const copy = readonly(demoDefaultForm)

const handleEmitDemo = (data: string) => console.log(data)

watch(
  () => demoDefaultForm.name,
  (newValue, oldValue) => {
    console.log('舊資料:', oldValue)
    console.log('新資料:', newValue)
  },
)
const timeoutID = window.setInterval(() => console.log('Hello!'), 1000)

onMounted(() => {
  console.log('mounted')
})

onUpdated(() => {
  console.log('updated')
})

onBeforeUnmount(() => {
  console.log('unmount')
  window.clearInterval(timeoutID)
})
</script>

<template>
  <main>
    <h1>This is the Home Page</h1>
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
      <section class="m-3">
        <h2 class="text-xl font-bold">v-model: {{ demoDefaultForm.name }}</h2>
        <InputDemo2 v-model:name="demoDefaultForm.name" />
      </section>
      <section class="m-3">
        <h2 class="text-xl font-bold">readonly: {{ copy.name }}</h2>
        <InputDemo2 v-model:name="copy.name" />
      </section>
    </div>
  </main>
</template>

<style scoped></style>
