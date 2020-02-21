<template>
  <div>
    <app-header />
    <main>
      <div class="st-container__flex">
        <search-bar />
        <list-content :lists="lists" />
      </div>
    </main>
    <app-footer />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'
@Component({
  components: {
    AppHeader: () => import('~/components/roofs/Header.vue'),
    AppFooter: () => import('~/components/roofs/Footer.vue'),
    SearchBar: () => import('~/components/roofs/SearchBar.vue'),
    ListContent: () => import('~/components/contents/ListContent.vue')
  }
})
class TopPage extends Vue {
  async asyncData () {
    const data = await require('~/static/json/store.json')
    return {
      lists: data
    }
  }
}
export default TopPage
</script>

<style lang="scss" scoped>
.st-container__flex {
  display: flex;
}
</style>
