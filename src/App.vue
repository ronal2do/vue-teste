
<script>
 
  import StqHero from './imports/hero.vue'
  import VcMenu from './imports/menu.vue'
  import StqFooter from './imports/footer.vue'

  export default {
    components:{ VcMenu, StqHero, StqFooter },
  }
</script>

<template>
  <div>
    <vc-menu></vc-menu>
    <stq-hero></stq-hero>
    <stq-footer></stq-footer>
  </div>
</template>


<style>
  body{ font-size: 16px; line-height: 1.5;}
  h1{font-size: 4em;}
  h2{font-size: 3.5em;}
  h3{font-size: 3em;}
  h4{font-size: 1.5em;}
 
</style>
