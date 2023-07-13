<script setup lang="ts">
import type { ITodo } from '../types'
const todos: ITodo[] = [
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
  {
    id: 4,
    task: 'Pay bills',
    description: 'Water, electric, gas, etc.',
    completed: false,
  },
  {
    id: 5,
    task: 'Call the doctor',
    description: 'Make an appointment for a checkup',
    completed: false,
  },
  {
    id: 6,
    task: 'Go to the gym',
    description: 'Workout for 30 minutes',
    completed: false,
  },
  {
    id: 7,
    task: 'Read a book',
    description: 'Catch up on your favorite book',
    completed: false,
  },
  {
    id: 8,
    task: 'Write a letter',
    description: 'Write to a friend or family member',
    completed: false,
  },
  {
    id: 9,
    task: 'Learn a new skill',
    description: 'Take an online course or read a book',
    completed: false,
  },
  {
    id: 10,
    task: 'Volunteer your time',
    description: 'Help out at a local soup kitchen or animal shelter',
    completed: false,
  },
  {
    id: 11,
    task: 'Volunteer your time',
    description: 'Help out at a local soup kitchen or animal shelter',
    completed: false,
  },
  {
    id: 12,
    task: 'Volunteer your time',
    description: 'Help out at a local soup kitchen or animal shelter',
    completed: false,
  },
  {
    id: 13,
    task: 'Volunteer your time',
    description: 'Help out at a local soup kitchen or animal shelter',
    completed: false,
  },
  {
    id: 14,
    task: 'Volunteer your time',
    description: 'Help out at a local soup kitchen or animal shelter',
    completed: false,
  },
]
</script>

<template>
  <main class="w-[300px] px-4 py-5 text-center text-gray-700 max-h-[1rem] overflow-">
    <Todo v-for="todo in todos" :key="todo.id" :todo="todo" />
    <!-- <div v-for="todo in todos" :key="todo.id" class="">
      {{ todo.task }}
    </div> -->
  </main>
</template>
