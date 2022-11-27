<script setup lang="ts">
defineProps<{
  loading: boolean
}>()
</script>

<template>
  <button
    class="p-1 shadow-md bg-gradient-to-tr from-blue-500 to-pink-900 rounded-md transition-all duration-500"
    :class="loading ? 'opacity-80 cursor-not-allowed' : ''"
  >
    <span
      class="font-medium text-white bg-gray-900 flex justify-center items-center gap-2 rounded-md py-2 transition-all ease-in-out hover:opacity-80 duration-500 tracking-wider font-mono h-10"
      :class="loading ? 'px-4 w-14' : 'px-6 w-32'"
    >
      <slot />
    </span>
  </button>
</template>
