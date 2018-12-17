<template>
  <div class="footer">
    <div class="footer-nav">
      <div class="footer-item">
        <div class="title-name">SUBMIT AND PROMOTED</div>
        <ul>
          <li>
            <nuxt-link :to="localePath('submitdapp')" class="nav-item">Submit a ÐApp</nuxt-link>
          </li>
          <li>
            <nuxt-link :to="localePath('promoteddapp')" class="nav-item">Promoted a ÐApp</nuxt-link>
          </li>
        </ul>
      </div>
      <div class="footer-item">
        <div class="title-name">ABOUT US</div>
        <ul>
          <li>
            <nuxt-link :to="localePath('about')" class="nav-item">About</nuxt-link>
          </li>
          <li>
            <nuxt-link :to="localePath('term')" class="nav-item">Terms of use</nuxt-link>
          </li>
        </ul>
      </div>
      <div class="footer-item">
        <div class="title-name">CONTACT US</div>
        <ul>
          <li>
            <a href="#" class="nav-item">Email</a>
          </li>
          <li>
            <a href="#" class="nav-item">Facebook</a>
          </li>
        </ul>
      </div>
      <div class="footer-item">
        <div class="title-name">FOLLOW US</div>
        <ul>
          <li>
            <a href="#" class="nav-item">Twitter</a>
          </li>
          <li>
            <a href="#" class="nav-item">Facebook</a>
          </li>
          <li>
            <a href="#" class="nav-item">Medium</a>
          </li>
          <li>
            <a href="#" class="nav-item">Github</a>
          </li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <div class="copy-box">Copyright © 2018 Link to ÐApps</div>
      <SiteSwitch/>
    </div>
  </div>
</template>

<script>
import SiteSwitch from '~/components/SiteSwitch'
export default {
  name: 'Footer',
  components: {
    SiteSwitch
  }
}
</script>
<style lang="scss" scoped>
@import '~assets/css/settings';

.footer {
  background-color: $color--black;
  padding: 30px 40px 0px;
  color: #aeaeae;
  text-decoration: none;
}
.footer-nav {
  display: flex;
  padding-bottom: 30px;
  border-bottom: 1px solid #aeaeae;
}
.footer-item {
  width: 240px;
  .title-name {
    font-weight: 500;
    line-height: 40px;
  }
  .nav-item {
    color: #aeaeae;
    text-decoration: none;
    line-height: 32px;
  }
}
.footer-bottom {
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
