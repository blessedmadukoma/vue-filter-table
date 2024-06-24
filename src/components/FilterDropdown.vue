<template>
  <div class="relative flex items-center w-full px-4">
    <button
      @click="showFilter = !showFilter"
      class="w-full flex items-center justify-center py-2 px-4 text-sm font-medium text-gray-900"
    >
      Filter
    </button>

    <div v-if="showFilter" class="absolute top-12 right-0 z-10 w-48 p-3 bg-white rounded-lg shadow">
      <h6 class="mb-3 text-sm font-medium text-gray-900">Status</h6>
      <ul class="space-y-2 text-sm">
        <li v-for="(status, index) in statuses" :key="index">
          <input
            @change="filter"
            type="checkbox"
            :id="`filter_option_${index}`"
            :value="status"
            class="w-4 h-4 bg-gray-100 border-gray-300 rounded-lg"
          />
          <label :for="`filter_option_${index}`" class="ml-2 text-sm font-medium text-gray-900">{{
            status
          }}</label>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { computed, ref } from 'vue'

const showFilter = ref(false)

const props = defineProps({
  items: {
    type: Array,
    required: true
  }
})

console.log('Prop items: ' + props.items)

const statuses = computed(() => {
  // retreive the unique status
  return [...new Set(props.items.map((item) => item.status))]
})

const emit = defineEmits(['filter'])

const filter = (e) => {
  emit('filter', e.target.value)
}
</script>
