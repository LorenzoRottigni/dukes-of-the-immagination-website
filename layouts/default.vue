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
</style>

<script>
export default {
    head(){
        return {
            title : 'the dukes of immagination',
            link: [{ rel:"stylesheet", type:"text/css", href:'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css' }]
        }
    }
}
</script>