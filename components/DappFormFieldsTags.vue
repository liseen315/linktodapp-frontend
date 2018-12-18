<template>
  <div>
    <p class="heading">
      Tags
      <span class="required">(at least 1 required)</span>
    </p>
    <div class="input-wrapper">
      <input :placeholder="'Add a tag'" type="text" class="input" autocomplete="off" maxlength="20">
      <span class="add"></span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {}
  }
}
</script>


<style lang="scss" scoped>
@import '~assets/css/settings';
.add {
  background: $color--black;
  color: $color--gray;
  display: inline-block;
  font-size: 0.75rem;
  font-weight: 700;
  text-transform: uppercase;
  padding: 3px 5px;
  opacity: 0.4;
  line-height: 1.2;
  transition: all 0.2s ease;
  &:hover {
    cursor: pointer;
  }
  &.--is-ready {
    opacity: 1;
  }
}

.dropdown {
  position: absolute;
  background: rgba($color--gray, 0.9);
  padding: 10px;
  box-shadow: 0 17px 70px rgba($color--black, 0.2);
  width: 320px;
  top: 37px;
  left: 0;
  overflow: hidden;
  z-index: 10;
  @include mediapoint('min-width', $mediapoint--default) {
    width: 350px;
  }
}

.dropdown-item {
  display: block;
  padding: 7px 28px 7px 10px;
  background: lighten($color--gray, 2%);
  box-shadow: 0 0 20px rgba($color--black, 0.1);
  text-decoration: none;
  position: relative;
  margin: 2px;
  &:hover {
    cursor: pointer;
  }
  &:after {
    content: '';
    position: absolute;
    right: 10px;
    bottom: 9px;
    width: 9px;
    height: 9px;
    transform: rotate(45deg);
  }
}

.dropdown-list {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
}

.heading {
  margin-top: 1.45rem !important;
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

.item {
  display: flex;
  align-items: center;
  margin: 5px;
  background: rgba(lighten($color--gray, 100%), 0.3);
  padding: 10px;
  box-shadow: 0 0 20px rgba($color--black, 0.05);
  border: 1px solid transparent;
  position: relative;
  &.--has-warning {
    border-color: $color--warning;
  }
}

.list {
  display: flex;
  flex-wrap: wrap;
  text-align: center;
  margin: -5px -5px 10px -5px;
}

.remove {
  cursor: pointer;
  margin-left: 8px;
  position: relative;
  top: 1px;
}

.warning-list {
  &.-tags {
    margin-bottom: 10px;
    padding: 10px;
  }
}
</style>
