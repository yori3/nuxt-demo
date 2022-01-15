<template>
  <div>
    <Header />
    <main>
      <div class="inner">
        <h1 class="title">{{ title }}</h1>
        <p class="publishedAt">{{ publishedAt }}</p>
        <div class="post" v-html="content"></div>
      </div>
    </main>
    <Footer />
  </div>
</template>

<script>
import axios from 'axios'
import Header from '@/components/siteHeader.vue'
import Footer from '@/components/siteFooter.vue'

export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://yori3.microcms.io/api/v1/news/${params.slug}`,
      {
        headers: { 'X-MICROCMS-API-KEY': '86d3f9d6-e86e-416a-84ab-7de805c462ae' }
      }
    )
    return data
  },
  components: {
    Header,
    Footer
  }
}
</script>