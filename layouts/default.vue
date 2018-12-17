<template>
  <div>
    <Header/>
    <div class="content">
      <nuxt/>
    </div>
    <Footer/>
  </div>
</template>

<script>
import Header from '~/components/Header'
import Footer from '~/components/Footer'
export default {
  components: {
    Header,
    Footer
  },
  watch: {
    $route(to, from) {
      console.log('route', from, to)
    }
  }
}
</script>

<style lang="scss" scoped>
.content {
  padding-top: 66px;
}
</style>
