<template lang="pug">
    header.d-flex.justify-content-around.align-items-center.shadow-lg
        ul.list-unstyled.mb-0.d-flex
            li.border-top.border-bottom.mx-3.border-dark.px-5.py-2
                nuxt-link.text-dark(to="/") ABOUT US
            li.border-top.border-bottom.mx-3.border-dark.px-5.py-2 
                nuxt-link.text-dark(to="/") HOME
        img(:src="require('~/static/dukes_of_immagination_logo.jpg')", alt="dukes of immagination logo")
        ul.list-unstyled.mb-0.d-flex.gap-3
            li.border-top.border-bottom.mx-3.border-dark.px-5.py-2 
                nuxt-link.text-dark(to="/") MISSION
            li.border-top.border-bottom.mx-3.border-dark.px-5.py-2 
                nuxt-link.text-dark(to="/exploit_dei_mastri_birrai") DISCOVER THE BOOK
</template>

<style lang="sass" scoped>
header
    z-index: 0
    img
        max-height: 30vh
</style>