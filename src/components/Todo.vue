<script setup lang="ts">
import type { ITodo } from '../types'

defineProps<{
  todo: ITodo
}>()
</script>

<template>
  <div>
    <p class="bg-red-900 m-5 text-white">
      {{ todo.task }} - {{ todo.id }}
    </p>
  </div>
</template>
