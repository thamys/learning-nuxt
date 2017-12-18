
<template lang="pug">
  #app
    #bg
    section.topIndex
      - var topSections = [{index: 5, name:'Festas'},{index: 6, name:'Vantagens'},{index: 7, name:'Vídeos'}, {index: 8, name:'Previsão dos custos'}]
      each topSection, index in topSections
        .circleIndex
          .circleIndex-number= topSection.index
          .circleIndex-text= topSection.name
    nuxt
    section.bottomIndex
      - var bottomSections = [{index:2, name:'Produção'},{index:3, name:'Atendimento'},{index:4, name:'Arrecadação'}]
      each bottomSection, index in bottomSections
        .circleIndex
          .circleIndex-number= bottomSection.index
          .circleIndex-text= bottomSection.name
    script(src="https://use.fontawesome.com/699336bbda.js")
</template>

<style lang="stylus">
  // VARS
  $main-color= #85c16b
  $text-color= #ffffff
  $contrast-color= #ed3200
  $help-color= #777f76
  $body-color= #2a362b

  $indexRule-border= 1px solid $main-color

  // Transition helpers
  $animationSpeed-normal= .3s
  $animationSpeed-slow= .5s
  $animationSpeed-fast= .2s

  body, html, #__nuxt, #app
  color $body-color
  font-family Montserrat, Helvetica, sans-serif
  min-height 100vh
  html *
    margin 0
    padding 0
  aside,
  div,
  section,
  header,
  nav,
  footer,
  body,
  #__nuxt,
  #app
    display flex
    flex-direction column
    position relative
  nav
    flex-direction row
  a,
  span,
  button
    align-items center
    display inline-flex
    position relative

  html *
    transition opacity $animationSpeed-normal, transform $animationSpeed-normal, visibility $animationSpeed-normal

  // INICIO
  body, #__nuxt, #app
    max-height 100vh
    overflow hidden
    & > *
      z-index 1
</style>

<script>
  
</script>