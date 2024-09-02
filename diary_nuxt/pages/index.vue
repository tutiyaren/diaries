<template>
  <div>
    <div class="wrapper">
      <h1>ホームページ</h1>
      <p>こちらはホームページのコンテンツです。</p>
      <h1>ホームページ</h1>
      <p>こちらはホームページのコンテンツです。</p>
      <h1>ホームページ</h1>
      <p>こちらはホームページのコンテンツです。</p>
      <h1>ホームページ</h1>
      <p>こちらはホームページのコンテンツです。</p>
    </div>

    <NavMenu />
  </div>
</template>

<script>
import NavMenu from '@/components/nav/menu.vue';

export default {
  components: {
    NavMenu,
  },
};
</script>

<style scoped>
.wrapper {
  margin-left: 10%;
}

@media screen and (max-width: 768px) {
  .wrapper {
    margin-left: 0;
  }
}
</style>
