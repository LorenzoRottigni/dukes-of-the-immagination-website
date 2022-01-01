<template lang="pug">
    .nuxt-app.h-100.d-flex.align-items-center
        //img.w-25.d-block.mx-auto(:src="require('~/static/beer.jpg')", alt="book cover")   
        h1.text-center.text-white.w-100 We are passionate people who love beer,books, and cyber
</template>

<style lang="sass">
    @font-face 
        font-family: daniel
        src: url('~/static/fonts/daniel.ttf')
    .nuxt-app
        background: rgb(2,0,36)
        background: radial-gradient(circle, rgba(2,0,36,1) 0%, rgba(0,0,0,1) 70%, #333333  100%)
        position: relative
        z-index: 2
        &::after
            content: ''
            position: absolute
            top: 0
            left: 0
            right: 0
            bottom: 0
            background-image: url('~/static/beer.jpg')
            background-repeat: no-repeat
            background-size: 25%
            background-position: center
            opacity: 0.4
            z-index: -1
        h1 
            font-family: daniel


    //background: rgb(2,0,36);
    //background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(0,0,0,1) 23%, rgba(81,75,85,1) 100%);
</style>