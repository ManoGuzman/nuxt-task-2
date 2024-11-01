<!-- pages/lifestyle/[...slug].vue -->
<script>
export default {
  async asyncData({ $content, params }) {
    const lifestyle = await $content("lifestyle", params.slug).fetch();
    const [prev, next] = await $content("lifestyle")
      .only(["title", "slug"])
      .sortBy("createdAt", "asc")
      .surround(params.slug)
      .fetch();
    return {
      lifestyle,
      prev,
      next,
    };
  },
  methods: {
    formatDate(date) {
      const options = { year: "numeric", month: "long", day: "numeric" };
      return new Date(date).toLocaleDateString("en", options);
    },
  },
};
</script>

<template>
  <div class="container">
    <HeaderView />
    <div class="row">
      <ContentDoc v-slot="{ doc }">
        <div class="three columns">
          <img class="u-max-full-width" :src="'/images/' + doc.image" />
        </div>
        <div class="six columns">
          <h4>{{ doc.title }}</h4>
          Periodista: {{ doc.journalist }}; Fecha: {{ doc.publishDate }}; Tipo
          de noticias: {{ doc.category }}
          <pre></pre>
          <h5>Nota</h5>
          <ContentRenderer :value="doc" />
          <PrevNextLifestyle />
        </div>
      </ContentDoc>
    </div>
    <FooterView />
  </div>
</template>