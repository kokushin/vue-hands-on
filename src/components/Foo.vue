<template>
  <h1>Foo</h1>
</template>

<script>
  console.log('foo')
</script>

<style scoped lang="scss">
  // scoped で ローカルスコープ化
  // lang="scss" でSCSS記法を有効化 要node-sass, sass-loader
  h1 {
    color: #333;
  }
</style>
