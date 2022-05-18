<template>
  <div>
    <script
      src="https://kit.fontawesome.com/43036f8826.js"
      crossorigin="anonymous"
    ></script>
    <Hero
      :heading="page.heading"
      :subheading="page.subheading"
      :image="page.image"
    />
    <div
      class="px-8 mx-auto mt-12 prose sm:px-6 md:px-4 lg:px-2 xl:px-0 xl:prose-xl lg:prose-lg md:prose-md"
    >
      <h3>
        {{ page.mainpitch.title }}
      </h3>
      <p>
        {{ page.mainpitch.description }}
      </p>
      <h2>
        {{ page.title }}
      </h2>
      <p>
        {{ page.description }}
      </p>
      <h4>
        {{ page.subpitch }}
      </h4>
      <div class="lg:grid lg:grid-cols-2 lg:gap-8">
        <div
          v-for="(example, index) in page.pics.examples"
          :key="index"
          class="flex flex-col items-center px-6 border rounded-lg shadow justify-top"
        >
          <img class="h-64" :src="example.image" />
          <p class="mt-2 text-justify">{{ example.text }}</p>
        </div>
      </div>
      <h4>
        {{ page.subpitch2 }}
      </h4>
      <div class="lg:grid lg:grid-cols-2 lg:gap-8">
        <div
          v-for="(example, index) in page.pics.examplesRooms"
          :key="index"
          class="flex flex-col items-center px-6 border rounded-lg shadow justify-top"
        >
          <img class="h-64" :src="example.image" />
          <p class="mt-2 text-justify">{{ example.text }}</p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  async asyncData({ $content }) {
    const page = await $content('beforeAfter').fetch()
    // const posts = await $content('blog').fetch()

    return {
      page,
      //   posts,
    }
  },
}
</script>
