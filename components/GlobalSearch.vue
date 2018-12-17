<template>
  <div class="component-global-search">
    <div class="search-input-wrapper">
      <input ref="searchInput" class="search-input" placeholder="Discover awesome ÐApps…">
    </div>
  </div>
</template>

<script>
export default {
  name: 'GlobalSearch'
}
</script>

<style lang="scss" scoped>
@import '~assets/css/settings';

.component-global-search {
  display: flex;
  align-items: center;
  background: rgba($color--black, 0.1);
  padding: 8px 12px;
  border-radius: 3px;
  min-width: 250px;
  transition: all 0.2s ease;
  position: relative;
  color: $color--black;
  &.is-searching {
    background: $color--white;
    box-shadow: 0 0 10px rgba($color--black, 0.1);
    border-bottom-left-radius: 0;
    border-bottom-right-radius: 0;
    input {
      color: $color--black;
    }
  }
  &.has-input {
    @include mediapoint('min-width', 975px) {
      min-width: 400px;
    }
  }
}

.search-input-wrapper {
  position: relative;
  z-index: 15;
  flex-grow: 1;
  padding-left: 8px;
}
.search-input {
  width: 100%;
  border: none;
  background: transparent;
  color: $color--black;
  &::placeholder {
    color: $color--black;
  }
  &.-white {
    color: $color--white;
    &::placeholder {
      color: $color--white;
      .is-searching & {
        color: $color--black;
      }
    }
  }
}
</style>
