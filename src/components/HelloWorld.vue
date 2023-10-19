<script setup lang="ts">
import { reactive, ref } from 'vue'

defineProps<{ msg: string }>()
const countRef = ref(false)
const state = reactive({
  countMet: {
    count: 0,
  },
})

const incrementRef = () => {
  countRef.value = !countRef.value
}

const increment = () => {
  state.countMet.count += 12
}
</script>

<template>
  <div class="title">
    <h1 v-if="countRef">{{ msg }}</h1>
  </div>

  <div class="card">
    <button type="button" @click="incrementRef">[Ref] count is {{}}</button>
    <button type="button" @click="increment">[Method] count is {{ state.countMet.count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank">create-vue</a>, the official Vue + Vite
    starter
  </p>
  <p>
    Install
    <a href="https://github.com/vuejs/language-tools" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.title {
  height: 6rem;
  background: pink;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  rotate: calc(180deg);
}

.read-the-docs {
  color: #888;
}
</style>
