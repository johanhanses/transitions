<script setup lang="ts">
defineProps<{
  show: boolean
  width?: string
}>()
</script>

<template>
  <button class="py-2 px-5 font-medium hover:bg-gray-700/50 rounded-md transition-colors duration-300">
    <slot />
  </button>
  <Transition
    enter-active-class="duration-300 ease-in"
    enter-from-class="transition-all opacity-0 -translate-y-5"
    enter-to-class="opacity-100 translate-y-0"
  >
    <div v-show="show" class="absolute bg-white shadow-md rounded-md top-full border border-pink-900" :class="width">
      <ul class="my-2">
        <slot name="menuItem" />
      </ul>
    </div>
  </Transition>
</template>
