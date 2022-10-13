<template>
  <div class="p-4 max-w-sm rounded shadow bg-white text-sky-900 h-80" v-show="selectedTitle === props.title">
    <slot />
  </div>
</template>

<script setup>
import { inject } from 'vue'

const props = defineProps({ title: String })
const selectedTitle = inject('selectedTitle')
</script>