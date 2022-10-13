<template>
  <ul class="w-full grid grid-cols-4 gap-1 mb-2">
    <li class=" cursor-pointer bg-gray-400 text-center rounded-lg hover:opacity-80" v-for="tab in tabs" @click="selectedTitle = tab">
      {{ tab }}
    </li>
  </ul>
  <slot />
</template>

<script setup>
import { provide, ref, useSlots } from 'vue'

const tabs = ref(useSlots().default().map(tab => tab.props.title))
const selectedTitle = ref(tabs.value[0])

provide('selectedTitle', selectedTitle)
</script>