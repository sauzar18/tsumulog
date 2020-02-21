<template>
  <n-link
    :to="`/${article.id}`"
    class="st-item"
  >
    <article>
      <div>
        <h3 class="text-orange">
          {{ article.name }}
        </h3>
        <address>{{ article.address }}</address>
        <p>{{ article.description }}</p>
      </div>
      <figure>
        <img
          :src="article.thumbnail"
          :alt="article.name"
        >
        <figcaption class="orange">
          {{ article.genre }}
        </figcaption>
      </figure>
    </article>
  </n-link>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'nuxt-property-decorator'
@Component
class ListItem extends Vue {
  @Prop({ type: Object, default: {} }) article
}
export default ListItem
</script>

<style lang="scss" scoped>
a {
  display: block;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.16);
  color: #000;
  padding: 10px;
  border-radius: 4px;
  &:hover,
  &:focus {
    background-color: #efefef;
  }
}
article {
  display: flex;
  flex-direction: row-reverse;
}
figure {
  display: flex;
  align-items: center;
  width: 240px;
  margin-right: 10px;
  flex-shrink: 0;
  position: relative;
}
figcaption {
  position: absolute;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 6px;
  height: 24px;
  font-size: 14px;
  top: 0;
  left: 0;
}
img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
}
h3 {
  margin-bottom: 8px;
}
p {
  font-size: 16px;
}
address {
  font-size: 14px;
  margin-bottom: 7px;
  color: rgb(143, 143, 143);
}
</style>
