<template>
  <div class="w-full">
    <section class="min-h-screen py-4 bg-blue-100">
      <h2 class="text-4xl text-center">ABOUT</h2>
    </section>
    <section class="min-h-screen py-4">
      <h2 class="text-4xl text-center">WORK</h2>
      <div class="flex flex-row flex-wrap">
        <div
          v-for="w in works.contents"
          :key="w.id"
          class="p-5 flex-none lg:w-1/3 md:w-1/2 sm:w-1/2 w-full transition duration-300 z-10"
        >
          <div class="max-w-lg rounded overflow-hidden shadow-lg mb-4">
            <div class="overflow-hidden w-full h-64">
              <img
                class="w-full h-64 object-cover"
                :src="w.image.url"
                :alt="w.name"
              />
            </div>
            <div class="px-6 py-4 pb-2 bg-white">
              <div class="font-bold text-xl mb-2">{{ w.name }}</div>
              <div>
                <small>{{ w.body }}</small>
              </div>
            </div>
            <div class="py-3">
              <span
                v-for="s in w.skill"
                :key="s"
                class="inline-block bg-yellow-100 rounded-full px-3 py-1 text-sm font-semibold text-yellow-500 hover:bg-yellow-200"
                >{{ s }}</span
              >
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="min-h-screen py-4 bg-blue-100">
      <h2 class="text-4xl text-center">SKILL</h2>
    </section>
  </div>
</template>

<script>
export default {
  async asyncData({ $microcms }) {
    const works = await $microcms.get({
      endpoint: "works",
    })
    return {
      works,
    }
  },
}
</script>
