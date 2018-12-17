<template>
  <div class="comp-menu">
    <div class="nameplate"></div>
    <ul class="nav-list">
      <li class="nav-item">
        <nuxt-link :to="localePath('index')" class="nav-link">{{ $t('header_home') }}</nuxt-link>
      </li>
      <li class="nav-item">
        <nuxt-link :to="localePath('alldapps')" class="nav-link">{{ $t('header_alldapps') }}</nuxt-link>
      </li>
      <li class="nav-item">
        <nuxt-link :to="localePath('ranking')" class="nav-link">{{ $t('header_ranking') }}</nuxt-link>
      </li>
      <li class="nav-item">
        <nuxt-link :to="localePath('topplayer')" class="nav-link">{{ $t('header_topplayers') }}</nuxt-link>
      </li>
      <li class="nav-item">
        <nuxt-link :to="localePath('stats')" class="nav-link">{{ $t('header_stats') }}</nuxt-link>
      </li>
    </ul>
    <ul class="nav-list-search">
      <li class="nav-item -search">
        <GlobalSearch/>
      </li>
    </ul>
    <div class="submit-dapp">
      <nuxt-link :to="localePath('submitdapp')" class="submit-btn">{{ $t('submitdapp') }}</nuxt-link>
    </div>
  </div>
</template>

<script>
import GlobalSearch from '~/components/GlobalSearch'
export default {
  components: {
    GlobalSearch
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/settings';

.comp-menu {
  display: flex;
  align-items: center;
  padding: 16px 10px;
  position: fixed;
  background: $color--gray;
  width: 100%;
  box-sizing: border-box;
  z-index: 2;
  @include mediapoint('min-width', 640px) {
    padding-left: 22px;
    padding-right: 22px;
  }
}
.nav-list {
  display: flex;
  align-items: center;
}
.nav-item {
  margin-left: 20px;
  display: flex;
  align-items: center;
  text-align: center;
  cursor: pointer;
}
.nav-link {
  text-decoration: none;
  display: flex;
  align-items: center;
  border: 1px solid transparent;
  border-left: 0;
  border-right: 0;
  position: relative;
  &.nuxt-link-exact-active {
    border-bottom: 1px solid $color--black;
  }
}
.submit-dapp {
  margin-left: auto;
}
.submit-btn {
  border: 1px solid #333;
  padding: 7px 10px;
  border-radius: 3px;
  border-color: hsla(0, 0%, 98%, 0.7);
  text-decoration: none;
  color: $color--white;
}
</style>
