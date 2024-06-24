<script setup>
import { onMounted, ref } from 'vue'

const data = ref([
  {
    id: 1,
    assigned_to: 'Alice',
    status: 'Pending',
    title: 'Complete project report',
    due_at: '2024-06-30'
  },
  {
    id: 2,
    assigned_to: 'Bob',
    status: 'In Progress',
    title: 'Update website',
    due_at: '2024-07-15'
  },
  {
    id: 3,
    assigned_to: 'Charlie',
    status: 'Completed',
    title: 'Prepare presentation',
    due_at: '2024-06-25'
  },
  {
    id: 4,
    assigned_to: 'Daniel',
    status: 'Blocked',
    title: 'Build web page',
    due_at: '2024-06-29'
  },
  {
    id: 5,
    assigned_to: 'Emmanuel',
    status: 'Pending',
    title: 'Design layout',
    due_at: '2024-04-25'
  },
  {
    id: 6,
    assigned_to: 'Arda',
    status: 'Blocked',
    title: 'Write project documentation',
    due_at: '2024-06-24'
  },
  {
    id: 7,
    assigned_to: 'Guler',
    status: 'Pending',
    title: 'Present hardware',
    due_at: '2024-06-26'
  },
  {
    id: 8,
    assigned_to: 'John',
    status: 'Blocked',
    title: 'Sketch product features',
    due_at: '2024-06-24'
  },
  {
    id: 9,
    assigned_to: 'Stones',
    status: 'Blocked',
    title: 'Assign tasks',
    due_at: '2024-06-24'
  }
])

const items = ref([])

onMounted(async () => {
  // const response = await fetch('http://localhost:8000/api/tasks')

  // items.value = await response.json()

  items.value = data.value
})
</script>

<template>
  <div class="p-8 bg-gray-100 min-h-screen">
    <!-- Table goes here! -->
    <DataTable :items="items" />
  </div>
</template>
