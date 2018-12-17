<template>
  <div class="site-switch">
    <span
      class="location"
      :class="{active:this.showLoaction}"
      @click.stop="showLocationList()"
    >{{ $t('change_location') }} &gt;</span>
    <ul class="site-list" v-show="this.showLoaction">
      <li v-for="locale in $i18n.locales" :key="locale.code" class="site-item">
        <nuxt-link :to="switchLocalePath(locale.code)" class="site-nav">{{ locale.name }}</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      showLoaction: false
    }
  },
  mounted: function() {
    document.addEventListener('click', this.onDocmentClickHandler)
  },
  methods: {
    showLocationList: function() {
      this.showLoaction = true
    },
    onDocmentClickHandler: function() {
      if (!this.$el.contains(event.target) && this.showLoaction) {
        this.hideLoaction()
      }
    },
    hideLoaction: function() {
      this.showLoaction = false
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/settings';
.site-switch {
  position: relative;
  .location {
    cursor: pointer;
    width: 140px;
    height: 40px;
    display: block;
    line-height: 40px;
    padding-left: 10px;
    &.active {
      background: #fff;
    }
  }
  .site-list {
    position: absolute;
    background-color: #fff;
    width: 150px;
    top: -73px;
  }
}
.site-item {
  padding: 10px;
}
.site-nav {
  text-decoration: none;
  &:hover {
    color: $color--purple;
  }
}
</style>
