<template>
  <div>
    <Header />
    <main>
      <section class="section">
        <div class="section__inner">
          <h2 class="section__title">News</h2>

          <div class="newsArchive">
            <div class="newsArchive__item" v-for="content in contents" :key="content.id">
              <nuxt-link :to="`/${content.id}`">
                <div class="newsArchive__meta">
                  <time class="newsArchive__date" v-html="dataSeparate(content.publishedAt)"></time>
                </div>
                <h3 class="newsArchive__title">{{ content.title }}</h3>
              </nuxt-link>
            </div>
          </div>
        </div>
      </section>

      <section class="section">
        <div class="section__inner">
          <h2 class="section__title">About</h2>
          <p @click="console.log('header')">このサイトについて</p>
        </div>
      </section>

      <section class="section">
        <div class="section__inner">
          <h2 class="section__title">Contact</h2>
          <div class="btn"><nuxt-link to="/contact" class="btn__link">お問合せはこちら</nuxt-link></div>
        </div>
      </section>
    </main>
    <Footer />
  </div>
</template>
<script>
import axios from 'axios'
import Header from '@/components/siteHeader.vue'
import Footer from '@/components/siteFooter.vue'
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
    methods: {
      dataSeparate: function(t){
        const year = t.slice( 0, 4 );
        const month = t.slice( 5, 7 );
        const day = t.slice( 8, 10 );
        const time = year + '年' + month + '月' + day + '日';
        return time;
      }
    },
    components: {
      Header,
      Footer
    }
  };
</script>

<style lang="scss">

</style>