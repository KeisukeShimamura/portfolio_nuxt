<template>
  <div class="w-full">
    <div class="h-96 bg-gray-500">
      メインビジュアル<br />
      full × 384px
    </div>
    <section class="p-5">
      <h2 class="text-4xl text-center font-serif my-5">ABOUT</h2>
      <div class="flex flex-row flex-wrap">
        <div class="sm:w-1/2 w-full">
          <img src="/image/20220226214616200_480x320.png" />
        </div>
        <div class="">
          <p class="text-3xl my-2 font-bold">嶋村 圭祐</p>
          <p class="my-1"><span class="font-bold">出身：</span>岡山県岡山市</p>
          <p class="my-1">
            <span class="font-bold">趣味：</span>サイクリング/ハイボール
          </p>
        </div>
      </div>
      <div class="my-4">
        大学卒業後は零細企業でSIerに就職し、業務システムなどを開発。<br />
        激務の中で開発を遂行するためのスキルや根気を身につける。<br />
        5年ほど働いたが、ブラック企業戦士になる前に倒れそうなため、転職を決意。<br />
        <br />
        前職の転勤で札幌へ引っ越したため、そのまま札幌で人材紹介企業に転職。<br />
        自社サービスサイトの保守、新規Webシステムの開発をメインに行い、<br />
        社内問い合わせチャットボットや営業リストのスクレイピングなどの開発以外のメンバーのサポートも実施。
      </div>
    </section>
    <section class="p-5 bg-blue-50">
      <h2 class="text-4xl text-center font-serif">WORK</h2>
      <div class="flex flex-row flex-wrap">
        <div
          v-for="w in works.contents"
          :key="w.id"
          class="p-5 lg:w-1/3 md:w-1/2 sm:w-1/2 w-full"
        >
          <WorkCard
            :title="w.name"
            :imageurl="w.image.url"
            :imagealt="w.name"
            :body="w.body"
            :skills="w.skill"
          ></WorkCard>
        </div>
      </div>
    </section>
    <section class="p-5">
      <h2 class="text-4xl text-center font-serif">SKILL</h2>
      <div class="flex flex-row flex-wrap">
        <SkillBar
          title="フロントエンド"
          :skills="frontendSkills.contents"
        ></SkillBar>
        <SkillBar
          title="バックエンド"
          :skills="backendSkills.contents"
        ></SkillBar>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  async asyncData({ $microcms }) {
    const works = await $microcms.get({
      endpoint: "works",
      queries: { orders: "publishedAt" },
    })
    const frontendSkills = await $microcms.get({
      endpoint: "skills",
      queries: {
        filters: "category[contains]フロントエンド",
        orders: "-score",
      },
    })
    const backendSkills = await $microcms.get({
      endpoint: "skills",
      queries: {
        filters: "category[contains]バックエンド",
        orders: "-score",
      },
    })
    return {
      works,
      frontendSkills,
      backendSkills,
    }
  },
}
</script>
