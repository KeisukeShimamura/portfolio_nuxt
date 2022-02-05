<template>
  <div>
    <h1>ポートフォリオ</h1>
    <section>
      <h2>ABOUT</h2>
    </section>
    <section>
      <h2>WORKS</h2>
    </section>
    <section>
      <h2>SKILL</h2>
      <div class="flex flex-wrap">
        <div
          v-for="w in works.contents"
          :key="w.id"
          class="max-w-sm rounded overflow-hidden shadow-lg mx-2"
        >
          <img class="w-full" :src="w.image.url" :alt="w.name" />
          <div class="px-6 py-4">
            <div class="font-bold text-xl mb-2">{{ w.name }}</div>
            <p class="text-gray-700 text-base">
              {{ w.body }}
            </p>
          </div>
          <div class="px-6 pt-4 pb-2">
            <span
              v-for="s in w.skill"
              :key="s"
              class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
              >#{{ s }}</span
            >
          </div>
        </div>
      </div>
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
