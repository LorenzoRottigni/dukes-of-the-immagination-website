<template lang="pug">
    .nuxt-app.h-100.py-3.d-flex.align-items-center.justify-content-center.flex-wrap
        //TITLE
        h1.text-white.text-center.mt-5.mb-4 L'exploit dei mastri birrai: un cyber thriller
        .container-fluid#slider-container.pb-3.pb-lg-0
            .row.align-items-center
                //SLIDER-LEFT if there are pages back
                #slider-left.bg-light(v-if="currentIndex > 0", @click="decrementCurrentIndex")
                    i.fas.fa-backward
                //IMAGE SECTION
                .col-8.offset-2.col-lg-3.offset-lg-2#slider-image-container
                    //display the current indexed images
                    img.rounded(:src=" slides[currentIndex].img_url ", alt="book image screens")
                .col-10.offset-1.col-lg-3.offset-lg-2.mt-5.mt-lg-0
                    //PARAGRAPH SECTION
                    #slider-text-container.rounded.shadow-lg
                        p.text-white.overflow-auto.p-3
                            //display the current indexed paragraph
                            | {{slides[currentIndex].paragraph}}
                        .p-3
                            //display if is the last slide
                            button.btn.btn-outline-light.w-100(v-if="currentIndex === 2")
                                    nuxt-link.text-reset(to="/exploit_dei_mastri_birrai") PURCHASE
                //SLIDER-RIGHT if there are pages next
                #slider-right.bg-light(v-if="currentIndex != 2",@click="incrementCurrentIndex")
                    i.fas.fa-forward
</template>

<script>

  //import gsap (animation library)
  import { gsap } from "gsap"

  export default {
      data(){
          return {
              slides : [
                  {
                      img_url : require('~/static/screens.jpg'),
                      paragraph : 'L’affascinante mondo del luppolo catalizza una storia che vede il bene e il male contrapposti, avvolti dalla modernità di un mondo non troppo distante dal nostro ed assolutamente plausibile. Ogni personaggio è sinergico ad un altro, nessuno è protagonista assoluto. Il contrasto è dietro ogni pagina, così come lo è la possibilità di apprendere un po’ di quella tecnologia, di quella scienza, di quel mondo cyber che per troppa gente rappresenta sinonimi di “irraggiungibile”, “fantascienza”, “troppo complicato”.'
                  },
                  {
                      img_url : require('~/static/couple.jpg'),
                      paragraph : 'Nel frattempo, la vostra parte limbica verrà guidata attraverso una serie di colpi di scena, di ribaltamenti e rallentamenti, di eventi inaspettati e di momenti normali. L’evoluzione della storia vi porterà per mano in una sequenza di alti e bassi fino all’apoteosi, il trionfo finale. La prima domanda che dovreste porvi prima ancora di aprire questo libro è: sarà il trionfo di chi? Del bene o del male? '
                  },
                  {
                      img_url : require('~/static/coding.jpg'),
                      paragraph : 'E la seconda: siete così sicuri che sia o possa essere solo finzione letteraria? Venite a scoprirlo. Vi aspettiamo.'
                  }
              ],
              currentIndex : 0
          }
      },
      methods : {
         /**
         * @description increment the current index of 1, animates the text container and the image container
         */
          incrementCurrentIndex(){
              gsap.to('#slider-image-container', { y : 1000 , duration : 1 })
              gsap.to('#slider-text-container', { y : 1000 , duration : 1 })

              /* sync gsap delay */
              setTimeout(()=>{
                  if(this.currentIndex === 2)
                      this.currentIndex = 0
                  else
                      this.currentIndex++
              }, 1000)

              gsap.to('#slider-image-container', { y : 0, duration : 1 , delay : 1})
              gsap.to('#slider-text-container', { y : 0 , duration : 1 , delay: 1})
          },
          /**
         * @description decrement the current index of 1, animates the text container and the image container
         */
          decrementCurrentIndex(){
              gsap.to('#slider-image-container', { y : 1000 , duration : 1 })
              gsap.to('#slider-text-container', { y : 1000 , duration : 1 })

              /* sync gsap delay */
              setTimeout(()=>{
                  if(this.currentIndex > 0)
                      this.currentIndex--
              }, 1000)

              gsap.to('#slider-image-container', { y : 0, duration : 1 , delay : 1})
              gsap.to('#slider-text-container', { y : 0 , duration : 1 , delay: 1})
          }
      }
  }

</script>

<style lang="sass" scoped>

  h1
      position: sticky
  img
      width: 100%
  #slider-text-container
      background-color: rgba(192, 192, 192, 0.4)
  #slider-container
      position: relative
      overflow-x: hidden

      ///////////////////////////
      // LEFT-RIGHT CONTROLLERS /
      ///////////////////////////

      #slider-left, #slider-right
          position: absolute
          top: 50%
          transform: translateY(-50%)
          height: 60px
          width: 60px
          display: flex
          align-items: center
          justify-content: center
          border-radius: 50%
          i
              font-size: 26px
      #slider-left
          left: 5%
      #slider-right
          right: 5%

  //less than 70px left-right-controllers fit to screen
  @media screen and (max-width: 700px)
      #slider-left
          left: 0 !important
          transform: translateX(-50%) !important
      #slider-right
          right: 0 !important
          transform: translateX(50%) !important

</style>
