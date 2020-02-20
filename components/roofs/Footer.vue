<template>
  <footer class="st-footer yellow">
    <div class="st-footer__inner st-container">
      <p><small>&copy;kento tsumuraya</small></p>
    </div>
  </footer>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'
@Component
class Footer extends Vue {
}
export default Footer
</script>

<style lang="scss" scoped>
.st-footer__inner {
  height: 40px;
  display: flex;
  align-items: center;
}
p {
  width: 100%;
  text-align: center;
}
</style>
