<template>
  <div
    class="card max-w-lg rounded-md overflow-hidden shadow-lg mb-4 bg-white cursor-pointer"
  >
    <div class="card-image overflow-hidden w-full h-64 relative">
      <img
        class="w-full h-64 object-cover transition duration-300"
        :src="imageurl"
        :alt="imagealt"
      />
    </div>
    <div class="px-6 py-4 pb-2">
      <div class="font-bold text-lg mb-2">{{ title }}</div>
      <div>
        <small>{{ body }}</small>
      </div>
    </div>
    <div class="py-3">
      <span
        v-for="s in skills"
        :key="s"
        class="inline-block bg-yellow-100 rounded-full mx-1 px-2 py-1 mb-2 text-xs font-semibold text-yellow-500"
        >{{ s }}</span
      >
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
    imageurl: {
      type: String,
      default: () => "",
    },
    imagealt: {
      type: String,
      default: () => "",
    },
    body: {
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

<style scoped>
.card:hover .card-image img {
  transform: scale(1.1);
}
.card .card-image::after {
  content: "Read More";
  background: rgba(0, 0, 0, 0.4);
  padding-top: 35%;
  @apply text-white opacity-0 absolute w-full h-full top-0 left-0 text-center text-xl;
}
.card:hover .card-image::after {
  @apply opacity-100;
}
</style>
