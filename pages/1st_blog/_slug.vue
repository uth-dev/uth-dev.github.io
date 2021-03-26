<template>
  <div class="">
    <v-chip
      v-if="chip1"
      class="ma-2"
      close
      @click:close="chip1 = false">
      Closable
    </v-chip>
    <article>
      <nuxt-content :document="article" />
    </article>
    <blog>
      <nuxt-content :document="blog" />
    </blog>
  </div>
</template>
<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content('1st_blog', params.slug).fetch()
    return {
      article,
    }
  },
}
</script>
<style>
.nuxt-content h2 {
  font-weight: bold;
  font-size: 28px;
}
.nuxt-content h3 {
  font-weight: bold;
  font-size: 22px;
}
</style>
