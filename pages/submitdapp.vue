<template>
  <div class="submit-container">
    <section class="section intro">
      <div class="container">
        <h1 class="title">Submit a ÐApp</h1>
      </div>
    </section>
    <section class="section form">
      <div class="container">
        <DappFormFields/>
      </div>
    </section>
  </div>
</template>

<script>
import DappFormFields from '~/components/DappFormFields'
export default {
  components: {
    DappFormFields
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/settings';
.section {
  &.intro {
    position: relative;
    .container {
      width: 800px;
      margin: 0 auto;
    }
    .title {
      text-align: center;
      padding-top: 20px;
    }
  }
  &.form {
    .container {
      display: flex;
      flex-direction: column;
      margin: 20px auto;
      @include mediapoint('min-width', $mediapoint--default) {
        margin: 30px auto 200px;
        flex-direction: row;
        width: 800px;
      }
    }
  }
}
</style>
