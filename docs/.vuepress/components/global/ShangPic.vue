<!--
 * @LineStart: -------------------------------------------
 * @Copyright: © 2020, itclanCoder. All rights reserved.
 * @LineEnd: ----------------------------------------------
 * @Product: 
 * @Mode Name: 
 * @Autor: vxPublic:itclanCoder
 * @Date: 2020-07-01 15:46:03
 * @Version: xxx.v1.0
 * @LastEditors: 川川
 * @LastEditTime: 2020-07-07 20:42:44
 * @Description: 
-->
<template>
  <div class="shang-wrap">
    <a
      target="_blank"
      href="https://www.zhi12.cn/paycenter/reward/widget?entity=user&id=33813"
    >
      <img
        height="80"
        v-if="shangeFlag"
        class="shange"
        src="/images/itclanCoder-shang.png"
      />
    </a>
  </div>
</template>

<script>
export default {
  name: 'ShangPic',
  data() {
    return {
      shangeFlag: false,
    };
  },

  mounted() {
    window.addEventListener('scroll', this.isShangImg);
  },

  destroyed() {
    window.removeEventListener('scroll', this.isShangImg);
  },

  methods: {
    // 为了计算距离顶部的高度，当高度大于60显示回顶部图标，小于60则隐藏
    isShangImg() {
      const that = this;
      let scrollTop =
        window.pageYOffset ||
        document.documentElement.scrollTop ||
        document.body.scrollTop;
      that.scrollTop = scrollTop;
      if (that.scrollTop > 60) {
        that.shangeFlag = true;
      } else {
        that.shangeFlag = false;
      }
    },
  },
};
</script>

<style lang="stylus" scoped>
.shang-wrap {
  width: 170px;
  height: 80px;
  position: fixed;
  bottom: 50px;
  right: 118px;
  z-index: 999999;
  opacity: 1;
  text-align: center;

  img {
    display: inline-block;
    vertical-align: center;
  }
}

@media screen and (max-width: 768px) {
  .shang-wrap img {
    width: 150px;
    height: 80px;
    position: fixed;
    right: 3.5rem;
    bottom: 50px;
    text-align: center;
    z-index: 777;
  }
}
</style>
