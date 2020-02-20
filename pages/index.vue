<template>
  <div>
    <app-header />
    <app-footer />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'
@Component({
  components: {
    AppHeader: () => import('~/components/roofs/Header.vue'),
    AppFooter: () => import('~/components/roofs/Footer.vue')
  }
})
class TopPage extends Vue {
}
export default TopPage
</script>
