<template>
  <div class="item">
    <p class="heading">Platform</p>
    <div class="selection-wrapper">
      <button
        :class="platform === 'Ethereum' ? 'is-active' : ''"
        class="selection"
        @click="setPlatform('Ethereum')"
      >Ethereum</button>
      <button
        :class="platform === 'EOS' ? 'is-active' : ''"
        class="selection"
        @click="setPlatform('EOS')"
      >EOS</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    platform: {
      type: String,
      required: true
    }
  },
  methods: {
    setPlatform(value) {
      this.$emit('updateField', 'platform', value)
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/settings';
.selection-wrapper {
  display: flex;
  align-items: center;
}

.selection {
  text-decoration: underline;
  width: 50%;
  border: 1px solid $color--black;
  border-left-width: 0;
  padding: 10px;
  transition: background 0.2s ease;
  &:first-child {
    border-left-width: 1px;
  }
  &.is-active {
    text-decoration: none;
    background: $color--black;
    color: $color--gray;
  }
}
</style>
