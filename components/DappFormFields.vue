<template>
  <div class="list">
    <DappFormFieldsName/>
    <DappFormFieldsEmail/>
    <DappFormFieldsDescription/>
    <DappFormFieldsWebsite/>
    <DappFormFieldsPlatform :platform="'Ethereum'"/>
    <DappFormFieldsContracts/>
    <DappFormFieldsStatus :status="'live'"/>
    <DappFormFieldsCategory/>
    <DappFormFieldsTags/>
  </div>
</template>

<script>
import DappFormFieldsName from '~/components/DappFormFieldsName'
import DappFormFieldsEmail from '~/components/DappFormFieldsEmail'
import DappFormFieldsDescription from '~/components/DappFormFieldsDescription'
import DappFormFieldsWebsite from '~/components/DappFormFieldsWebsite'
import DappFormFieldsPlatform from '~/components/DappFormFieldsPlatform'
import DappFormFieldsContracts from '~/components/DappFormFieldsContracts'
import DappFormFieldsStatus from '~/components/DappFormFieldsStatus'
import DappFormFieldsCategory from '~/components/DappFormFieldsCategory'
import DappFormFieldsTags from '~/components/DappFormFieldsTags'

export default {
  components: {
    DappFormFieldsName,
    DappFormFieldsEmail,
    DappFormFieldsDescription,
    DappFormFieldsWebsite,
    DappFormFieldsPlatform,
    DappFormFieldsContracts,
    DappFormFieldsStatus,
    DappFormFieldsCategory,
    DappFormFieldsTags
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/settings';

.list {
  width: 100%;
  max-width: 400px;
  padding: 10px;
  margin: 0 auto;
  @include mediapoint('min-width', $mediapoint--default) {
    margin-right: 20px;
    margin-left: 0;
  }
  .item {
    width: 100%;
    margin-bottom: 15px;
    position: relative;
    border: 1px solid transparent;
  }

  /deep/ .required {
    display: inline-block;
    padding-left: 2px;
    color: $color--error;
  }

  /deep/ .remaining-characters {
    position: absolute;
    display: block;
    right: 20px;
    top: 30px;
    font-size: 12px;
  }

  /deep/ .label {
    position: absolute;
    left: 0;
    top: 10px;
    padding: 20px;
    pointer-events: none;
    font-size: 12px;
    transition: top 0.2s ease;
  }

  /deep/ .text-input,
  /deep/ .text-area {
    border: none;
    padding: 30px 50px 30px 20px;
    width: 100%;
    box-shadow: 0 0 20px rgba($color--black, 0.05);
    box-sizing: border-box;
    background: rgba(lighten($color--gray, 100%), 0.9);
    transition: background 0.2s ease;
    &:focus {
      background: none;
      background: rgba(250, 250, 250, 0.7);
    }
    &:focus + .label,
    &.--is-filled + .label {
      top: -11px;
      opacity: 0.65;
    }
  }
}
</style>
