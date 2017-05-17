<script type="text/babel">
  import vco from 'vco'
  import {observer, inject} from 'utils/mobx-wechat'
  const WechatStore = 'system/wechat'
  const MemberStore = 'wechat/member'
  @inject(MemberStore, WechatStore)
  @observer
  export default class extends vco.app {
    async onLaunch(options) {
      await this.store[MemberStore].InitMember()// 会员初始化
      this.store[WechatStore].InitRoute(options)// 路由初始化
      this.store[WechatStore].getSystem()
      this.mazingMember = this.store[MemberStore].member// 约定token
    }
  }

</script>
<style rel="stylesheet/less">
  @import "less/color";
  .container {
    box-sizing: border-box;
    width: 100%;
    overflow-x: hidden;
  }
</style>
