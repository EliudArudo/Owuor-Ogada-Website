<template>
  <div class="full-width flex-center flex-column">
    <div class="full-width homepage-section overview">&nbsp;</div>
    <div class="full-width homepage-section sectors">&nbsp;</div>
    <div class="full-width homepage-section services">&nbsp;</div>
    <div class="full-width homepage-section products">&nbsp;</div>
    <div class="full-width homepage-section downloads">&nbsp;</div>
    <div class="full-width homepage-section partners">&nbsp;</div>
    <div class="full-width homepage-section form">&nbsp;</div>
    <div class="full-width homepage-section software">&nbsp;</div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component({
  components: {},
})
export default class IndexPage extends Vue {}
</script>

<style scoped>
.homepage-section {
  margin-top: 10px;
  background: rgba(0, 0, 0, 0.02);
}

.overview {
  min-height: 200px;
}

.sectors {
  min-height: 400px;
}

.services {
  min-height: 300px;
}

.products {
  min-height: 400px;
}

.downloads {
  min-height: 250px;
}

.partners {
  min-height: 400px;
}

.form {
  min-height: 350px;
}

.software {
  min-height: 200px;
}
</style>

