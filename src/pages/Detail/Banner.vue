<template>
  <div>
  <div class="banner" @click="handleBannerClick">
    <img class="banner-img" :src="bannerImg" />
    <div class="banner-info">
      <div class="banner-tittle">{{this.sightName}}</div>
      <div class="banner-number"> <span class="iconfont banner-icon">&#xe626;</span>36</div>
    </div>
  </div>
    <fade-Animation>
    <common-gallary :imgs="bannerImgs"
                    v-show="gallaryShow"
                    @close="handleGallyClose"
    ></common-gallary>
    </fade-Animation>
  </div>
</template>

<script>
  import CommonGallary from 'common/gallary/Gallary'
  import fadeAnimation from 'common/fade/fadeAnimation'
  export default {
    name: 'DetailBanner',
    components : {
      CommonGallary,
      fadeAnimation
    },
    props : {
      sightName : String,
      bannerImg : String,
      bannerImgs: Array
    },
    data () {
      return {
        gallaryShow :false

      }
    },
    methods :{
      handleBannerClick () {
        this.gallaryShow = true
      },
      handleGallyClose () {
        this.gallaryShow = false
      }
    }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
      .banner-tittle
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        height: .32rem
        line-height: .32rem
        margin-top: .14rem
        padding: 0 .4rem
        border-radius: .2rem
        background: rgba(0, 0, 0, .8)
        font-size: .24rem
        .banner-icon
          font-size: .24rem

</style>
