<template lang="pug">
    header.container-fluid.shadow-lg
        .row
            ul.col-4.list-unstyled.mb-0.d-flex.align-items-center
                li.border-top.border-bottom.mx-3.border-dark.px-5.py-2(
                    :class="currentRoute === 'home' ? 'active' : ''",
                    @click="setCurrentRoute('home')"
                )
                    nuxt-link.text-dark(to="/") HOME
                li.border-top.border-bottom.mx-3.border-dark.px-5.py-2(
                    :class="currentRoute === 'discover' ? 'active' : ''",
                    @click="setCurrentRoute('discover')"
                )
                    nuxt-link.text-dark(to="discover") DISCOVER THE BOOK
            .col-4
                img(:src="require('~/static/dukes_of_immagination_logo.jpg')", alt="dukes of immagination logo")
            ul.col-4.list-unstyled.mb-0.d-flex.gap-3.align-items-center
                li.border-top.border-bottom.mx-3.border-dark.px-5.py-2(
                    :class="currentRoute === 'manifest' ? 'active' : ''",
                    @click="setCurrentRoute('manifest')"
                ) 
                    nuxt-link.text-dark(to="/manifest") MANIFEST
                li.border-top.border-bottom.mx-3.border-dark.px-5.py-2(
                    :class="currentRoute === 'buy' ? 'active' : ''",
                    @click="setCurrentRoute('buy')"
                ) 
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
        width: 100%
        max-height: 25vh
    li
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