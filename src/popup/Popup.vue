<script setup lang="ts">
import type { ITodo } from '../types'
const todos = ref<ITodo[]>([
  {
    id: 1,
    task: 'Buy groceries',
    description: 'Milk, eggs, bread, etc.',
    completed: false,
  },
  {
    id: 2,
    task: 'Clean the house',
    description: 'Vacuum, dust, mop, etc.',
    completed: false,
  },
  {
    id: 3,
    task: 'Do laundry',
    description: 'Wash, dry, fold, put away',
    completed: false,
  },
])

const task_text = ref('')

const inputField = ref<any>(null)

function changeListener(checked: boolean, id: number) {
  const index = todos.value.findIndex(todo => todo.id === id)
  if (index !== -1)
    todos.value[index].completed = checked
}

function addTodo() {
  if (task_text) {
    todos.value.unshift({
      id: Date.now(),
      task: task_text.value,
      description: '',
      completed: false,
    })
    task_text.value = ''
  }
}
</script>

<template>
  <main class="w-[300px] px-4 py-5 text-center text-gray-700">
    <div class="mb-6 flex items-center">
      <svg class="h-8 w-8 stroke-current text-gray-600" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
        stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
          d="M20 13V6a2 2 0 00-2-2H6a2 2 0 00-2 2v7m16 0v5a2 2 0 01-2 2H6a2 2 0 01-2-2v-5m16 0h-2.586a1 1 0 00-.707.293l-2.414 2.414a1 1 0 01-.707.293h-3.172a1 1 0 01-.707-.293l-2.414-2.414A1 1 0 006.586 13H4" />
      </svg>
      <h4 class="ml-3 text-lg font-semibold">
        My Tasks
      </h4>
    </div>
    <Todo v-for="todo in todos" :key="todo.id" :todo="todo"
      @on-change="(checked: boolean) => changeListener(checked, todo.id)" />
    <div class="mt-2 flex h-8 w-full items-center rounded px-2 text-sm font-medium">
      <button @click="inputField.focus()">
        <svg class="h-5 w-5 fill-current text-gray-400" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
          stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6" />
        </svg>
      </button>
      <input ref="inputField" v-model="task_text" class="ml-4 h-8 flex-grow bg-transparent font-medium focus:outline-none"
        type="text" placeholder="add a new task" @keyup.enter="addTodo">
    </div>
  </main>
</template>
