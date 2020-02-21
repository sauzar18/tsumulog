<template>
  <article class="st-item">
    <div>
      <h3 class="ft-kosugi">
        <a
          :href="article.url"
          target="_blank"
          rel="noopener"
          class="text-red"
        >
          {{ article.name }}
        </a>
      </h3>
      <address>
        <a
          :href="article.maps"
          target="_blank"
          rel="noopener"
        >
          {{ article.address }}
        </a>
      </address>
      <p>{{ article.description }}</p>
      <div class="st-sns">
        <a
          v-if="article.instagram"
          :href="article.instagram"
          target="_blank"
          rel="noopener"
        >
          <i>
            <img src="~static/images/instagram.svg" alt="instagram">
          </i>
        </a>
      </div>
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
article {
  display: flex;
  flex-direction: row-reverse;
  width: 100%;
  > div {
    width: 100%;
  }
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
  line-height: 1.7;
  margin-bottom: 8px;
  font-size: 20px;
  a {
    &:hover,
    &:focus {
      text-decoration: underline;
    }
  }
}
p {
  font-size: 16px;
}
address {
  font-size: 14px;
  margin-bottom: 7px;
  a {
    color: rgb(143, 143, 143);
    &:hover,
    &:focus {
      color: #000;
    }
  }
}
.st-sns {
  display: flex;
  margin-top: 10px;
  i {
    display: flex;
    align-items: center;
  }
  img {
    width: 30px;
  }
}
</style>
