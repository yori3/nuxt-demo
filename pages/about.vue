<template>
  <div id="app">
    <Header />
    <main>

      <h1 class="pageTitle">About</h1>
      <section class="section">
        <div class="section__inner">
          <h2 class="section__title">このサイトについて</h2>
        </div>
      </section>
    </main>
    <Footer />
  </div>
</template>
<script>
import Header from '@/components/siteHeader.vue'
import Footer from '@/components/siteFooter.vue'
export default {
  components: {
    Header,
    Footer
  }
}
</script>
