<template>
  <div>
    <h1>{{ title }}</h1>
    <button v-on:click="changeTitle">Change</button>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        title: 'Foo'
      }
    },
    methods: {
      changeTitle () {
        this.title = 'Bar'
      }
    }
  }
</script>

<style scoped lang="scss">
  // scoped で ローカルスコープ化
  // lang="scss" でSCSS記法を有効化 要node-sass, sass-loader
  h1 {
    color: #333;
  }
</style>
