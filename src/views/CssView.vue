<template>
  <ul class="list">
    <li
      class="item"
      :class="{ cur: index === curIndex }"
      v-for="(item, index) in 5"
      :key="index"
      @click="curIndex = index"
    >
      {{ item }}
    </li>
  </ul>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  setup () {
    const curIndex = ref<number>(0)

    return {
      curIndex,
    }
  }
})
</script>

<style scoped>
.cur {
  color: red;
}
</style>