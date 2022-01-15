<template>
  <div>
    <Header />
    <main>
      <nuxt />
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
  };
</script>