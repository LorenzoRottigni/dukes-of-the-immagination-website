<template lang="pug">

    .nuxt-app.h-100.d-flex.align-items-center
        h1.text-center.text-white.w-100 We are passionate people who love beer, books, and cyber

</template>

<style lang="sass">

    //import font /static/fonts/daniel.ttf
    @font-face
        font-family: daniel
        src: url('~/static/fonts/daniel.ttf')
    .nuxt-app
        //nuxt /pages background
        //black bg
        background: rgb(0,0,0)
        //radient background black to gray
        background: radial-gradient(circle, rgba(0,0,0,1) 0%, rgba(0,0,0,1) 63%, rgba(102,102,102,1) 100%)
        position: relative
        overflow: auto
        z-index: 2
        //overlay background-image
        &::after
            content: ''
            position: absolute
            top: 0
            left: 0
            right: 0
            bottom: 0
            background-image: url('~/static/main-bg.png')
            background-repeat: no-repeat
            background-size: 60%
            background-position: center
            opacity: 0.4
            z-index: -1
        h1
            font-family: daniel

    //overlay background-image resize
    @media screen and (max-width: 500px)
      .nuxt-app
        &::after
          background-size: 90%
    @media screen and (min-width: 501px) and (max-width: 700px)
      .nuxt-app
        &::after
          background-size: 70%

</style>
