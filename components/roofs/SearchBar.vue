<template>
  <nav class="st-searchbar">
    <div>
      <h2>絞り込み検索</h2>
      <input-field
        id="filterWord"
        v-model="filterWord"
        label="絞りこみ検索"
        type="text"
      />
    </div>
    <figure>
      <img src="~static/images/ref_nomikai.jpg" alt="月一飲み会">
    </figure>
  </nav>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'
@Component({
  components: {
    InputField: () => import('~/components/forms/InputField.vue')
  }
})
class SearchBar extends Vue {
  filterWord: string = ''
}
export default SearchBar
</script>

<style lang="scss" scoped>
.st-searchbar {
  width: 320px;
  padding: 16px;
  display: flex;
  flex-direction: column;
}
h2 {
  font-size: 16px;
  margin-bottom: 16px;
  font-weight: normal;
}
figure {
  width: 100%;
  margin-top: auto;
}
img {
  width: 100%;
}
</style>
