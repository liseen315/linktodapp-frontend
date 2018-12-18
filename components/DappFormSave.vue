<template>
  <div class="wrapper">
    <div class="profile-score-wrapper">
      <h3 class="profile-score-title">
        Current profile strength
        <span class="profile-score-title-pct">100%</span>
      </h3>
    </div>
    <div class="submit-reason">
      <label class="text-area-label" for="submitReason">
        So we can better serve your needs,
        <strong>tell us what results you hope to achieve</strong> by submitting your ÐApp (this will not be made public).
      </label>
      <textarea class="text-area" name="submitReason" placeholder="I hope that..."/>
    </div>
    <div class="checkboxes">
      <div class="checkbox-field">
        <input id="subscribe-newsletter-checkbox" class="checkbox-input" type="checkbox">
        <label
          class="checkbox-label"
          for="subscribe-newsletter-checkbox"
        >Email me (very occasional) updates</label>
      </div>
      <div class="checkbox-field">
        <input id="accepted-terms-checkbox" class="checkbox-input" type="checkbox">
        <label class="checkbox-label" for="accepted-terms-checkbox">
          I accept the&nbsp;
          <nuxt-link to="/terms">Terms of Service</nuxt-link>&nbsp;
          <span class="required">(required)</span>
        </label>
      </div>
      <p>Submissions are free and typically processed by the next business day.</p>
    </div>
    <input :value="'Submit'" class="submit --is-ready" type="submit">
  </div>
</template>

<style lang="scss" scoped>
@import '~assets/css/settings';

.wrapper {
  width: 100%;
  max-width: 400px;
  padding: 10px;
  margin: 0 auto;
  margin-top: 1px;
  position: sticky;
  top: 19px;
  @include mediapoint('min-width', $mediapoint--default) {
    margin-left: 0;
    margin-right: 0;
  }
}

.text-area-label {
  display: block;
  padding-bottom: 5px;
}

.required {
  display: inline-block;
  padding-left: 2px;
  color: $color--error;
}

.submit {
  display: block;
  border-radius: 4px;
  margin: 0 auto;
  width: 300px;
  margin-top: 15px;
  border: none;
  background: rgba($color--black, 0.1);
  color: $color--black;
  font-size: 1rem;
  font-weight: 600;
  padding: 15px;
  position: relative;
  transition: all 0.5s ease;
  @include mediapoint('min-width', $mediapoint--default) {
    margin-left: 0;
    margin-right: 0;
  }
  &.--is-ready {
    background: rgba($color--black, 1);
    box-shadow: 0 17px 70px rgba($color--black, 0.3);
    color: $color--gray;
    &:hover {
      cursor: pointer;
    }
    &:active {
      top: 1px;
    }
  }
}

.title {
  margin: 0;
  font-size: 1.5rem;
}

.text-area {
  width: 100%;
  height: 60px;
  resize: none;
  padding: 10px;
  border: none;
  margin-top: 5px;
  box-sizing: border-box;
  box-shadow: 0 0 20px rgba($color--black, 0.05);
}

.url {
  width: 300px;
}

.submit-reason {
  background: darken($color--gray, 4%);
  width: 300px;
  padding: 10px;
  margin: 15px auto 0 auto;
  @include mediapoint('min-width', $mediapoint--default) {
    margin-left: 0;
    margin-right: 0;
  }
}

.checkboxes {
  margin: 12px auto 0;
  width: 300px;
  @include mediapoint('min-width', 900px) {
    margin-left: 0;
  }
}

.checkbox-field {
  margin-top: 9px;
  display: flex;
}

.checkbox-input {
  display: none;
  position: relative;
  &:checked + .checkbox-label:after {
    transform: scale(1);
  }
}

.checkbox-label {
  padding-left: 22px;
  position: relative;
  display: flex;
  &:before {
    cursor: pointer;
    content: '';
    display: block;
    width: 13px;
    height: 13px;
    border: 1px solid $color--black;
    position: absolute;
    top: 1px;
    left: 0;
  }
  &:after {
    cursor: pointer;
    content: '';
    display: block;
    background: $color--black;
    transition: transform 0.1s ease;
    transform: scale(0);
    width: 9px;
    height: 9px;
    position: absolute;
    top: 4px;
    left: 3px;
  }
}
</style>
