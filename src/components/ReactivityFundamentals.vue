<!-- // ----- NON SETUP SCRIPT ----- -->
<!-- <script>
import { ref } from 'vue'

export default {
  setup() {
    const count = ref(0)

    function increment() {
      // .value is needed in JavaScript
      count.value++
    }

    // don't forget to expose the function as well.
    return {
      count,
      increment
    }
  }
}
</script> -->

<script setup>
import { nextTick, reactive, ref } from 'vue'

const count = ref(0)

const obj = ref({
  nested: { count: 0 }
})

async function increment() {
  count.value++
  await nextTick()
}
// function mutateDeeply() {
//   obj.value.nested.count++
// }

const state = reactive({ count: 0 })
</script>

<template>
  <button @click="increment">Tambah Angka</button>
  <div>{{ state.count }}</div>
</template>
