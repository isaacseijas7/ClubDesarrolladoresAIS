<template>
  <div class="home1 mutlti-vendor">
    <menu-area/>
    <child/>
    <footer-area/>
  </div>
</template>

<script>
import MenuArea from '~/components/MenuArea'
import FooterArea from '~/components/FooterArea'
export default {
  name: 'BasicLayout',
  components: {
    MenuArea,
    FooterArea
  }
}
</script>

<style lang="scss">

</style>
