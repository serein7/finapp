<script>
import Icon from '@/components/icon/Icon'

export default {
  components: {
    Icon
  },

  props: {
    background: {
      type: String,
      default: null
    },
    icon: {
      type: String,
      default: null
    },
    className: {
      type: String,
      default: null
    },
    title: {
      type: String,
      default: null
    }
  }
}
</script>

<template lang="pug">
.d-button(
  :class="className"
  :style="{ background: background }"
  @click="$emit('onClick')"
)
  .d-button__icon(v-if="icon")
    div(:class="icon")
  .d-button__title {{ title }}
</template>

<style lang="stylus">
@import "~@/stylus/variables/animations"
@import "~@/stylus/variables/media"
.d-button-cirle
  display flex
  align-items center
  justify-content center
  width 40px
  height 40px
  font-size 16px
  color var(--c-font-4)
  background var(--c-bg-2)
  border 1px solid var(--c-bg-7)
  box-shadow 2px 2px 6px 0px var(--c-bg-2)
  border-radius 50px

  /.theme-light &
    box-shadow 2px 2px 6px 0px var(--c-bg-11)

  &:active:not(._disable)
    color var(--c-font-3)
    transform scale(0.96)

  &:hover:not(._disable)
    @media $media-laptop
      color var(--c-font-3)
      background var(--c-bg-1)
      border-color var(--c-bg-8)

  &._disable
    opacity .6
</style>

<style lang="stylus" scoped>
@import "~@/stylus/variables/animations"
@import "~@/stylus/variables/margins"
@import "~@/stylus/variables/media"
@import "~@/stylus/variables/fonts"

.d-button
  width 100%
  display flex
  align-items center
  // min-height 40px
  padding $m7 $m8
  color var(--c-font-2)
  cursor pointer
  anim-background()

  &:active
    transform scale(0.96)

  &._blue
    display inline-flex
    align-items center
    justify-content center
    // height 52px
    font-header-2()
    font-size 16px
    color var(--c-font-1)
    font-weight 600
    letter-spacing 1.6px
    background var(--c-blue-1)
    border-radius $m3

    &:hover
      @media $media-laptop
        background var(--c-blue-2)

  &._bdb
    border-bottom 1px solid var(--c-bg-5)
    &:hover
      @media $media-laptop
        background var(--c-bg-5)
    &:active
      background var(--c-bg-5)

  &._inline
    display inline-flex
    width auto

  &._center
    align-items center
    justify-content center

  &._grey
    background var(--c-bg-5)
    color var(--c-font-2)
    border-radius $m3

    /.theme-light &
      color var(--c-font-1)
      background var(--c-bg-12)

    &:hover
      @media $media-laptop
        background var(--c-bg-6)
        /.theme-light &
          background var(--c-bg-13)

  &._small
    height 40px
    padding 0 $m7
    color var(--c-font-4)
    background var(--c-bg-2)
    border 1px solid var(--c-bg-7)
    box-shadow 2px 2px 6px 0px var(--c-bg-2)
    border-radius $m3

    /.theme-light &
      box-shadow 2px 2px 6px 0px var(--c-bg-11)

    ^[0]:active &
      color var(--c-font-3)
      transform scale(0.96)

    ^[0]:hover &
      @media $media-laptop
        color var(--c-font-3)
        background var(--c-bg-1)
        border-color var(--c-bg-8)

  &__icon
    width 24px
    margin-left (- $m4)
    margin-right $m6
    font-size 20px
    text-align center
    opacity .85
</style>
