<template>
  <div>
    <ul class="list">
      <li class="item">
        <div class="name">Ethereum Mainnet Contracts</div>
        <div class="input-wrapper">
          <textarea
            :value="mainnet"
            class="input"
            placeholder="Enter addresses (one per line)"
            maxlength="11000"
          />
          <ul class="error-list -contracts">
            <li class="error-item"></li>
          </ul>
        </div>
      </li>
      <li class="item">
        <div class="name">EOS Mainnet Contracts</div>
        <div class="input-wrapper">
          <textarea
            :value="eosMainnet"
            class="input"
            placeholder="Enter EOS accounts (one per line)"
            maxlength="11000"
          />
          <ul class="error-list -contracts">
            <li class="error-item"></li>
          </ul>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      mainnet: '',
      eosMainnet: ''
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/settings';
.error-list {
  &.-contracts {
    padding: 10px;
  }
}

.heading {
  font-weight: 700;
  margin-top: 1.5rem;
  margin-bottom: 0.5rem;
}

.input-wrapper {
  &.--has-errors {
    border-color: $color--error;
  }
}

.item {
  margin-bottom: 5px;
}

.name {
  padding: 8px 0 8px 20px;
}

.input-wrapper {
  flex-grow: 1;
  box-shadow: 0 0 20px rgba($color--black, 0.05);
  border: 1px solid transparent;
  background: rgba(lighten($color--gray, 100%), 0.9);
}

.input {
  display: block;
  resize: none;
  min-height: 75px;
  width: 100%;
  padding: 10px 20px;
  border: none;
  box-sizing: border-box;
}
</style>
