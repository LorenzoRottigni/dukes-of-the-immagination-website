<template lang="pug">
    header.container-fluid.shadow-lg
        .row
            ul.col-10.offset-1.col-lg-4.offset-lg-0.my-3.my-lg-0.list-unstyled.mb-0.d-flex.align-items-center.justify-content-center.order-2.order-lg-1
                li.border-top.border-bottom.mx-3.border-dark.px-5.py-2(
                    @click="setCurrentRoute('home')"
                )
                    img(:src="require('~/static/pen-black.png')", v-if="currentRoute === 'home'")
                    nuxt-link.text-dark(to="/") HOME
                li.border-top.border-bottom.mx-3.border-dark.px-5.py-2(
                    @click="setCurrentRoute('discover')"
                )
                    img(:src="require('~/static/pen-black.png')", v-if="currentRoute === 'discover'")
                    nuxt-link.text-dark(to="discover") DISCOVER THE BOOK
            .col-10.offset-1.col-lg-4.offset-lg-0.order-1.order-lg-2.text-center
                img(:src="require('~/static/dukes_of_immagination_logo.jpg')", alt="dukes of immagination logo")
            ul.col-10.offset-1.col-lg-4.offset-lg-0.my-3.my-lg-0.list-unstyled.mb-0.d-flex.gap-3.align-items-center.justify-content-center.order-3
                li.border-top.border-bottom.mx-3.border-dark.px-5.py-2(
                    @click="setCurrentRoute('manifest')"
                ) 
                    img(:src="require('~/static/pen-black.png')", v-if="currentRoute === 'manifest'")
                    nuxt-link.text-dark(to="/manifest") MANIFEST
                li.border-top.border-bottom.mx-3.border-dark.px-5.py-2(
                    @click="setCurrentRoute('buy')"
                ) 
                    img(:src="require('~/static/pen-black.png')", v-if="currentRoute === 'buy'")
                    nuxt-link.text-dark(to="/exploit_dei_mastri_birrai") BUY THE BOOK
</template>

<script>

export default {
    data(){
        return {
            currentRoute : 'home'
        }
    },
    methods:{
        setCurrentRoute(route){
            this.currentRoute = route
        }
    }
}
</script>
<style lang="sass" scoped>

header
    z-index: 0
    img
        //width: 100%
        max-height: 25vh
    li
        position: relative
        img
            position: absolute
            left: 0
            top: 50%
            transform: translateY(-50%)
            width: 60px
            

        a
            white-space: nowrap
.active
    text-decoration: underline
    position: relative
    &::after
        content: ''
        position: absolute
        left: 0
        top: 50%
        width: 60px
        height: 200%
        background-size: cover
        background-repeat: no-repeat
        background-image: url('~/static/pen.png')
        transform: translateY(-50%) translateX(-5px) rotate(-10deg)
        border-radius: 30px
</style>