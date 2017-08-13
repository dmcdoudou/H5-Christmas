<template>
  <div id="p6">

    <top-layers :show_menu="true" :show_award_btn="false">
      <cartoon robot="ledi" class="robot1"></cartoon>
      <cartoon robot="huang" class="robot2"></cartoon>
      <cartoon robot="mei" class="robot3"></cartoon>
    </top-layers>

    <div class="content">

      <div class="dialog" v-if="award === '一等奖'">
        <div class="msg"></div>
        <div class="award"></div>
        <div class="form">
          <div class="input_wrap">
            <input class="input" placeholder="请输入您的地址" id="addr" type="text"/>
          </div>
          <div class="input_wrap">
            <input class="input" placeholder="请输入您的电话" id="tel" type="tel"/>
          </div>
          <btn btn_name="ci"></btn>
        </div>
      </div>

      <div class="dialog" v-else-if="['二等奖', '三等奖', '四等奖', '五等奖'].includes(award)">
        <div class="msg"></div>
        <div class="msg2"></div>
        <div class="luckybag"></div>
        <div class="msg3"></div>
      </div>

      <div class="dialog" v-else>
        <div class="msg4"></div>
      </div>

      <div class="award_rule">
        <div class="word"></div>
        <div class="detail_wrap">
          <div class="btn_detail" @click="showGift = !showGift"></div>
          <div class="award_detail" v-show="showGift">
            <img src="./image/gift_detail.png"/>
          </div>
        </div>
      </div>

    </div>

  </div>
</template>

<script>
  import TopLayers from '../../base/top_layers/TopLayers'
  import Cartoon from '../../base/cartoon/Cartoon'
  import Btn from '../../base/Btn/Btn'

  export default {
    name: 'p6',
    components: {
      'top-layers': TopLayers,
      'cartoon': Cartoon,
      'btn': Btn
    },
    data () {
      return {
        award: this.$route.params.award,
        showGift: false
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  @import "style/p6";
</style>
