<template lang="pug">
    .app.d-flex.flex-column
        //component Header
        Header
        main.flex-grow-1
            //the nuxt application containing all routes in /pages
            Nuxt
        //component Footer
        Footer
</template>

<style lang="sass" scoped>
    //nuxt application
    .app
      height: 100vh
      overflow-y: auto
      overflow-x: hidden
    *
      scroll-behavior: smooth
    //background under the pages
    main
      background-image: url('~/static/doi-spiral.svg')
      background-repeat: no-repeat
      background-size: 30%
      background-position: center
      scroll-behavior: smooth
    a
      white-space: nowrap
</style>

<script>
  export default {
      head(){
          return {
              title : 'the dukes of imagination',
              link: [{ rel:"stylesheet", type:"text/css", href:'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css' }],
              script: [
                  {
                  src: "https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js",
                  integrity: "sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p",
                  crossorigin: "anonymous"
                  }
              ]
          }
      }

  }
</script>
