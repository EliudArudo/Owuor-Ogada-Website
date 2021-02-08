<template>
  <div class="full-width flex-center flex-column page">
    <div class="full-width page-navigation-container">&nbsp;</div>
    <div class="full-width pagination-container">&nbsp;</div>
    <div class="full-width flex-center flex-row page-contents-container">
      <div class="center-section full-section">&nbsp;</div>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component({
  components: {},
})
export default class OurTeamPage extends Vue {}
</script>

<style scoped>
.pagination-container {
  height: 50px;
  background: rgba(0, 0, 0, 0.02);
}
</style>
