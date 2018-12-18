<template>
  <div>
    <p class="heading">
      Category
      <span class="required">(required)</span>
    </p>
    <div class="input-wrapper">
      <div class="input">
        <span class="selected-category">{{ 'Select a category' }}</span>
      </div>
      <transition name="fade">
        <div class="dropdown" v-if="dropdown">
          <ul class="categories">
            <li class="category"></li>
          </ul>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      categories: [],
      dropdown: false
    }
  }
}
</script>


<style lang="scss" scoped>
@import '~assets/css/settings';

.category {
  cursor: pointer;
  font-weight: 700;
  font-size: 0.85rem;
  text-transform: uppercase;
  padding: 5px 10px;
  margin: 0 -10px;
  &:hover {
    background: $color--gray;
  }
}

.dropdown {
  position: absolute;
  background: $color--white;
  padding: 10px;
  box-shadow: 0 17px 70px rgba($color--black, 0.2);
  border-top: 1px solid $color--gray;
  width: 320px;
  top: 36px;
  left: 0;
  overflow: hidden;
  z-index: 10;
  @include mediapoint('min-width', $mediapoint--default) {
    width: 350px;
  }
}

.heading {
  margin-top: 1.25rem !important;
  margin-bottom: 1rem !important;
}

.input {
  border: none;
  background: none;
  width: 100%;
  &::placeholder {
    color: $color--black;
  }
  &:focus::placeholder {
    color: rgba($color--black, 0.5);
  }
}

.input-wrapper {
  background: rgba(lighten($color--gray, 100%), 0.9);
  display: flex;
  width: 100%;
  padding: 10px;
  box-shadow: 0 0 20px rgba($color--black, 0.05);
  margin-bottom: 10px;
  position: relative;
  box-sizing: border-box;
}

.selected-category {
  text-decoration: underline;
  cursor: pointer;
}
</style>
