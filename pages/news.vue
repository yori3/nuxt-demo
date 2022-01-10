<template>
	<div>
		<Header />
		<main>
      <div id="content">
        <div class="inner">
          <h1>お知らせ一覧</h1>
          <div class="newsList">
            <div class="newsList__item" v-for="content in contents" :key="content.id">
              <nuxt-link :to="`/${content.id}`">
                <h2>{{ content.title }}</h2>
              </nuxt-link>
            </div>
          </div>
        </div>
      </div>
		</main>
		<Footer />
	</div>
</template>

<script>
import axios from 'axios';
import Header from "@/components/header.vue";
import Footer from "@/components/footer.vue";

export default {
  async asyncData() {
    const { data } = await axios.get(
      'https://yori3.microcms.io/api/v1/news',
      {
        headers: { 'X-MICROCMS-API-KEY': '86d3f9d6-e86e-416a-84ab-7de805c462ae' }
      }
    )
    return data
  },
  components: {
    Header,
    Footer
  },
}
</script>

<style lang="scss" scoped>

.newsList{
  &__item{
    margin-bottom: 1.5em;
    h2{
      color: #666;
    }
  }
}


</style>