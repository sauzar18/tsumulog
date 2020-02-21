<template>
  <header class="st-header white">
    <div class="st-header__inner st-container">
      <h1>つむログ</h1>
    </div>
  </header>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'
@Component
class Header extends Vue {
}
export default Header
</script>

<style lang="scss" scoped>
.st-header__inner {
  height: 60px;
  display: flex;
  align-items: center;
}
h1 {
  font-size: 27px;
}
</style>
