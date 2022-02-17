<template>
  <div class="md:w-1/2 w-full">
    <div class="text-center">
      {{ title }}
    </div>
    <div v-for="s in skills" :key="s.id" class="relative w-full h-10 mb-4">
      <div class="bg-red-200 text-white w-1/2" :data-score="s.score">
        {{ s.name }}
        <span class="">{{ s.score }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: () => "",
    },
    skills: {
      type: Array,
      default: () => {},
    },
  },
}
</script>
