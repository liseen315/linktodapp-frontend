<template>
  <div>
    <p class="heading">
      ÐApp status
      <span class="required">(required)</span>
    </p>
    <ul class="list">
      <li
        v-for="(item, index) in items"
        :key="index"
        :class="status === item ? 'item -' + item + ' --is-selected' : 'item -' + item"
      >{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    status: {
      type: String,
      required: true
    }
  },
  data: function() {
    return {
      items: [
        'live',
        'beta',
        'prototype',
        'wip',
        'concept',
        'broken',
        'stealth',
        'abandoned'
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/settings';

.heading {
  margin-top: 1.5rem !important;
}

.item {
  width: calc(50% - 10px);
  margin: 5px;
  background: $color--white;
  padding: 10px;
  box-shadow: 0 0 20px rgba($color--black, 0.05);
  border: 1px solid transparent;
  box-sizing: border-box;
  &:hover {
    cursor: pointer;
  }
  &.--is-selected {
    border-color: $color--black;
  }
}

.list {
  display: flex;
  flex-wrap: wrap;
  text-align: center;
  margin: 0 -5px 10px;
}
</style>
