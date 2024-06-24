<script setup>
const emit = defineEmits(['search'])

const emitSearch = (e) => {
  emit('search', e.target.value)
}
</script>

<template>
  <form class="px-4 py-3 flex items-center">
    <label for="Search" class="sr-only">Search</label>
    <div class="relative w-full">
      <input
        type="text"
        @input="emitSearch"
        placeholder="Search"
        class="bg-gray-50 border border-gray-300 p-2 rounded-lg"
      />
    </div>
  </form>
</template>
