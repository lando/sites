<template>
  <div id="vuepress-theme-blog__post-layout" class="post-content">
    <div class="vuepress-blog-theme-content">
      <h1 class="post-title">{{ $frontmatter.title }}</h1>
      <PostHeader
        :name="$frontmatter.author"
        :pic="$frontmatter.pic"
        :link="$frontmatter.link"
        :date="$frontmatter.date"
        :location="$frontmatter.location"
      />
      <CarbonAds />
      <Content />
      <hr />
      <Newsletter />
      <PostFooter
        :tags="$frontmatter.tags"
        :original="$frontmatter.original"
      />
    </div>
    <Toc />
  </div>
</template>

<script>
import CarbonAds from '@theme/components/CarbonAds.vue';
import PostHeader from '@theme/components/PostHeader.vue';
import PostFooter from '@theme/components/PostFooter.vue';
import Toc from '@theme/components/Toc.vue';

export default {
  components: {CarbonAds, PostHeader, PostFooter, Toc}, // eslint-disable-line
  mounted() {
    console.log(this);
  },
};
</script>

<style lang="stylus">
.post-content
  .carbon-ads
    position: fixed
    max-height: 100vh
    max-width: 320px
    overflow-y: auto
    padding-top: 8em
    top: 0
    right: 10px
    box-sizing: border-box
    z-index: 0
  #special_sponsors
    opacity .8
    position: fixed
    padding-top: 8em
    top: 0
    left 0
    z-index: 0
  .vuepress-toc
    padding-top: 250px
    max-width: 295px
    width: 295px
  hr
    border-top: 1px dotted #ddd
  .custom-block
    &.caption
      background-color: #f8f8f8
      padding: .1em 1em
      color: $landoBlue
      font-size: .8em
      font-weight: 700
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif
    &.thumbnail
      border: 1px dashed #ccc
      padding: 1em
.vuepress-blog-theme-content
  font-size 16px
  letter-spacing 0px
  font-family PT Serif, Serif
  color $textColor
  position relative
  .post-title
    padding-top 0
@media (max-width: $MQSmall)
  .post-content
    .carbon-ads
      position: relative
      float: right
      padding: 2em
      max-height: 100vh
      max-width: 300px
      overflow-y: auto
      z-index: 0
      border: 1px solid lighten($landoGrey, 90%)
      margin: 2em
@media (max-width: $MQMobile)
  .vuepress-blog-theme-content
    padding-top 0
  .post-title
    margin-top 0
</style>
