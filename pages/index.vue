<template lang="pug">
  .page
    section.content
      Aside 
      section.text
        aside.index
          span 1
        article.details
          header
            h2 Assessoria
          p Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean euismod bibendum laoreet.
            br
            | Proin gravida dolor sit amet lacus accumsan et viverra justo commodo.
          nav
            button.button Veja como funciona
              i.material-icons arrow_forward
    aside.sidePanel
      nav.articleSelector
        .articleSelector-item.articleSelector-item-active
          i.articleSelector-item-icon.material-icons pie_chart
          span.articleSelector-item-text Financeiro
        .articleSelector-item
          i.articleSelector-item-icon.material-icons insert_chart
          span.articleSelector-item-text Contábil
        .articleSelector-item
          i.articleSelector-item-icon.material-icons contact_mail
          span.articleSelector-item-text Jurídica
      section.articles
        article.articles-vertical
          header
            h2 Financeiro
            h3 Lorem ipsum dolor sit amet, consectetur adipiscing elit.
              br
              | Aenean euismod bibendum laoreet.
          p Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean euismod bibendum laoreet. Proin gravida dolor sit amet lacus accumsan et viverra justo commodo. Proin sodales pulvinar tempor. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam fermentum, nulla luctus pharetra vulputate, felis tellus mollis orci, sed rhoncus sapien nunc eget.
</template>

<script>
import Aside from '~/components/Aside.vue'

export default {
  components: {
    Aside
  }
}
</script>

<style lang="stylus">
  #bg
    background-image url('~/assets/background.png')
    background-repeat no-repeat
    background-size cover
    background-position center
    height 100%
    position absolute
    width 100%
    z-index 0
    &::before
      // background rgba(0,0,0,.5)
      content ''
      height 100%
      transition background .5s
      width 100%

  // RULERS
  .topIndex, .bottomIndex
    height 20vh
    transition height .3s
    will-change height
  .topIndex
    border-bottom $indexRule-border
  .bottomIndex
    border-top $indexRule-border

  // Main row
  .content
    align-items center
    flex-basis 100%
    flex-direction row
    flex-grow 1
  .sideBar
    height 100%
    padding 0 10px
    transition all .3s
    width calc(50vh - 50px)
    will-change width
  .navButton
    color white
    cursor pointer
    left 16px
    opacity 0
    position fixed
    text-shadow 1px 1px 1px rgba(0,0,0,.5)
    top 16px
    transform rotate(-60deg)
    transition all .4s, visibility .2s
    visibility hidden
  .logo
    align-items center
    flex-direction row
    img
      height auto
      width 100%
  .links
    &-wrapper
      flex-direction row
      justify-content space-evenly
      margin-top 10px
      position absolute
      transition transform .3s, opacity .3s, visibility .3s
      width 100%
      a
        color white
        flex-direction column
        margin-top 5px
        text-decoration none
        text-transform uppercase
        text
          decoration none
          transform uppercase
        &::after
          background white
          content ''
          height 2px
          display block
          transform scaleX(0)
          transition .4s
          width 100%
        &:hover::after
          transform scaleX(1)
          transition .2s
  .text
    color white
    flex 1
    text-shadow 1px 1px 1px rgba(0,0,0,.5)
  .details
    margin auto
    max-width 80%
    padding-left 4em
    p
      font-style italic
      font-weight 100
    header
      font-size 46px
      font-weight bold
      margin-bottom .3em
      &::after
        content ''
        background-color $main-color
        box-shadow 0px 1px 1px 0px rgba(0,0,0,.5)
        display block
        height 8px
        margin-top 8px
        width 46px
  .button
    background transparent
    border 1px solid rgba(255,255,255,.9)
    border-radius 6px
    font-family Dosis
    font-size 18px
    text-transform uppercase
    font-weight 500
    color white
    cursor pointer
    margin-top 16px
    opacity 1
    outline none
    padding 6px 12px
    transition background .2s
    &:hover
      background-color rgba(0,0,0,.3)
    i
      font-weight 300
      margin-left 1em
  .sidePanel
    background-color #FAFFFA
    box-shadow -2px 0 3px 0 rgba(0,0,0,.3)
    flex-direction row-reverse
    height 100%
    position absolute
    right 0
    transform translateX(110%)
    transition transform .2s
    width 65vw
  .articleSelector
    margin 100px 16px 100px 0
    flex-direction column
    justify-content space-evenly
    &::before
      border-left 1px dashed black
      content ''
      height 100%
      position absolute
    &-item
      margin 20px 16px
      &::before
        background gray
        content ''
        display block
        height 100%
        margin-left -19px
        position absolute
        transform scaleY(.5)
        transform-origin 50% 0
        width 7px
      & > *
        margin 3px 0
        color $help-color
      &-active
        color $main-color
        & > *
          color $main-color
        &::before
          background $main-color
          transform scaleY(1)
      &-text
        font-family Dosis
        text-transform uppercase
  .articles
    flex 1
    padding 25px 15px
    & > article
      header
        h2
          color $main-color
          font-family Montserrat
          font-size 42px
          font-weight bold
        h3
          color #2a362b
          font-family Dosis
          font-size 28px
          font-weight 600
          text-transform uppercase
          margin 10px 0 25px
          

  // States
  .content-collapsed
    #bg
      transform translateX(-300px)
      transition .6s
      &::before
        background rgba(0,0,0,.8)
    .topIndex, .bottomIndex
      height 10px
    .sideBar
      width 100px
    .links-wrapper
      opacity 0
      transform scale(0)
      visibility hidden
    .navButton
      visibility visible
      opacity 1
      transform rotate(0deg)
    .text
      transform translate(-90px, -30vh)
      max-width 300px
      header
        font-size 24px
        font-weight 600
        margin-bottom 0px
        &::after
          transform scaleY(0)
          visibility hidden
    .button
      visibility hidden
      opacity 0
    .sidePanel
      transform translateX(0%)

  // Wheel circle
  .logo::before
    border-color white
    border-radius 50%
    border-style dashed
    border-width 1px
    content ''
    position absolute
    left 10px
    transform translateX(calc(-50% - 10px))
    transition all .3s, background .2s
    height calc(100vh - 10px)
    width calc(100vh - 40px)
    will-change background, border, height, transform, width
    z-index -1
  .content-collapsed
    .logo::before
      background white
      border-color $main-color
      border-style solid
      border-width 3px
      transition all .3s, top .27s, background .6s
      transform translateX(-25px)
      height 130px
      width 130px
  .index
    align-items center
    flex-direction row
    height 100%
    position absolute
    span
      background rgba(29, 68, 43, .95)
      border 1px solid white
      border-radius 50%
      font-family Dosis
      font-size 48px
      font-weight 900
      height 80px
      justify-content space-around
      transform translateX(-24px)
      width 80px
  .circleIndex
    align-items center
    color white
    flex-direction row
    margin 10px 0
    &-number
      align-items center
      border 1px solid white
      border-radius 50%
      height 1em
      justify-content space-around
      margin-right .5em
      padding .25em
      width 1em
  .content-collapsed
    .circleIndex
      transform translateX(-100vw) scale(0)
      opacity 0

</style>
