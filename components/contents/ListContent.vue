<template>
  <section class="st-list">
    <h2>グルメ一覧</h2>
    <ul>
      <li
        v-for="item in lists"
        :key="item.id"
      >
        <list-item :article="item" />
      </li>
    </ul>
  </section>
</template>

<style lang="scss" scoped>
</style>

<script lang="ts">
import { Component, Vue, Prop } from 'nuxt-property-decorator'
@Component({
  components: {
    ListItem: () => import('~/components/parts/ListItem.vue')
  }
})
class ListContent extends Vue {
  @Prop({ type: Array, default: () => ([]) }) lists
}
export default ListContent
</script>

<style lang="scss" scoped>
.st-list {
  padding: 16px;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.16) inset;
  width: calc(100% - 320px);
}
h2 {
  font-size: 18px;
  border-bottom: 2px solid #ffa952;
  margin-bottom: 16px;
}
li {
  margin-bottom: 16px;
  &:last-child {
    margin-bottom: 0;
  }
}
</style>
