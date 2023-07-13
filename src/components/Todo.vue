<script setup lang="ts">
import type { ITodo } from '../types'

defineProps<{
  todo: ITodo
}>()

const emit = defineEmits(['onChange'])
</script>

<template>
  <div>
    <input :id="todo.id.toString()" class="hidden" type="checkbox" :checked="todo.completed"
      @change="(e: any) => emit('onChange', e.target.checked)">
    <label class="flex h-10 cursor-pointer items-center rounded px-2 hover:bg-gray-100" :for="todo.id.toString()">
      <span
        :class="`${todo.completed ? 'bg-[#10B981] border-[#10B981] text-white' : 'border-gray-300 text-transparent'} flex h-5 w-5 items-center justify-center rounded-full border-2`">
        <svg class="h-4 w-4 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
          <path fill-rule="evenodd"
            d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
            clip-rule="evenodd" />
        </svg>
      </span>
      <span :class="`${todo.completed && 'text-[#9CA3AF] line-through'} ml-4 text-sm`">{{ todo.task }}</span>
    </label>
  </div>
</template>
