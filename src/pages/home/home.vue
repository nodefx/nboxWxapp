<template>
  <view>
  {{route}}
  {{system}}
  </view>
</template>

<script>
  import vco from 'vco'
  import {observer, inject} from 'utils/mobx-wechat'
  const systemStore = 'system/wechat'
  var app = getApp()
  @inject(systemStore)
  @observer
  export default class extends vco.page {

    state() {
      return {
        route: JSON.stringify(this.store[systemStore].member),
		system: JSON.stringify(this.store[systemStore].system),
      }
    }


    async onShow(options) {
    }

    async onLoad(options) {
    }

  }
</script>

<style rel="styltsheet/less">
</style>
