<template lang="pug">
    //////////////////////////////////////
    // HEADER                           //
    //////////////////////////////////////
    header.container-fluid.shadow-lg
        .row
            //UNORDERED LIST LEFT
            ul.col-12.col-lg-4.offset-lg-0.my-3.my-lg-0.list-unstyled.mb-0.d-flex.align-items-center.justify-content-center.order-2.order-lg-1.px-0
                // HOME LIST ITEM
                li.w-50.text-center.border-top.border-bottom.mx-3.border-dark.py-2(
                    @click="setCurrentRoute('home')"
                )
                    //displayed on active
                    img.d-none.d-md-block(:src="require('~/static/pen-black.png')", v-if="currentRoute === 'home'")
                    nuxt-link.text-dark(to="/") HOME
                // DISCOVER THE BOOK LIST ITEM
                li.w-50.text-center.border-top.border-bottom.mx-3.border-dark.py-2(
                    @click="setCurrentRoute('discover')"
                )
                    //displayed on active
                    img.d-none.d-md-block(:src="require('~/static/pen-black.png')", v-if="currentRoute === 'discover'")
                    nuxt-link.text-dark(to="discover") DISCOVER THE BOOK
            //CENTRAL IMAGE
            .col-10.offset-1.col-lg-4.offset-lg-0.order-1.order-lg-2.text-center
                img(:src="require('~/static/dukes_of_immagination_logo.jpg')", alt="dukes of immagination logo")
            //UNORDERED LIST LEFT
            ul.col-12.col-lg-4.offset-lg-0.mb-3.my-lg-0.list-unstyled.mb-0.d-flex.align-items-center.justify-content-center.order-3.px-0
                // MANIFEST LIST ITEM
                li.w-50.text-center.border-top.border-bottom.mx-3.border-dark.py-2(
                    @click="setCurrentRoute('manifest')"
                )
                    //displayed on active
                    img.d-none.d-md-block(:src="require('~/static/pen-black.png')", v-if="currentRoute === 'manifest'")
                    nuxt-link.text-dark(to="/manifest") MANIFESTO
                // MANIFEST LIST ITEM
                li.w-50.text-center.border-top.border-bottom.mx-3.border-dark.py-2(
                    @click="setCurrentRoute('buy')"
                )
                    //displayed on active
                    img.d-none.d-md-block(:src="require('~/static/pen-black.png')", v-if="currentRoute === 'buy'")
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
          /**
           * @description sets the new active route
           * @param {string} route
           */
          setCurrentRoute(route){
              this.currentRoute = route
          }
      }
  }

</script>

<style lang="sass" scoped>

  header
      z-index: 0
      //NAVBAR BRAND IMAGE
      img
          //width: 100%
          max-width: 100%
          max-height: 25vh
      li
          position: relative
          //STYLO IMAGE ON ACTIVE
          img
              position: absolute
              left: 0
              top: 50%
              transform: translateY(-50%)
              width: 60px

</style>
