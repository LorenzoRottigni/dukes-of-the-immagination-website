<template lang="pug">
    .app.d-flex.flex-column
        Header
        main.flex-grow-1
            Nuxt
        Footer
</template>

<style lang="sass" scoped>
    .app
        height: 100vh
        overflow: auto
</style>

<script>
export default {
    head(){
        return {
            title : 'the dukes of immagination',
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