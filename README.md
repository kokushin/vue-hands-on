# Vue.js社内向けハンズオン

## アジェンダ

1. Vue.jsについて
2. vue-cliを利用して環境構築&クイックスタート
3. コンポーネントを作ってみる
4. コンポーネント内のデータの操作
5. 便利なツール・ライブラリ紹介（時間あれば）

## Vue.jsについて

https://jp.vuejs.org/v2/guide/

- 読みやすい、書きやすい、なんとなく動きを予測できる
- 部分的にVueを利用することも容易
- 単一ファイルコンポーネントを利用可能（拡張子は `.vue`）。HTML, CSS, JavaScriptをまとめて記述することが可能
- フレームワーク、ライブラリが豊富

## vue-cliを利用して環境構築&クイックスタート

https://github.com/vuejs/vue-cli

- `vue-cli` と呼ばれるコマンドラインツールを利用することで、簡単に開発をスタートできる
- WebpackやPWAなどテンプレートが用意されており、用途に応じて選択可能

### 1. パッケージをインストール

`npm install vue-cli -g`

### 2. テンプレートを選択

`vue init webpack`

### 3. 必要モジュールをインストール

`npm install`

### 4. 開発スタート！

`npm run dev`

### 5. 完成したらビルド！

`npm run build`

## コンポーネントを作ってみる

`Foo` というコンポーネントを作成し、実際に出力してみる

1. `src/components` 配下に `Foo.vue` を作成
2. `Foo.vue` に `<template>, <script>, <style>` を記述 [変更箇所を確認する](https://github.com/kokushin/vue-hands-on/commit/24ed3318d676662fb722f9cf0fdee949f4d46e50)
3. `router/index.js` へ `Foo.vue` を読み込ませ、ルーティングする
4. `/foo` へアクセスし、`Foo.vue` の内容が出力されていることを確認 [変更箇所を確認する](https://github.com/kokushin/vue-hands-on/commit/67d501f0067f33b112fdf119558acbac7154781b)

※ルーティングとは → https://router.vuejs.org/ja/essentials/getting-started.html

## コンポーネント間のデータの操作

### 値の書き換え

`Foo` コンポーネントの `h1` の値を動的に変更してみる

1. `<template>` 内に `<button v-on:click="changeTitle">Change</button>` を追加
2. `data` に `title` の初期値 `Foo` を設定
3. `<h1>` 内のテキストを `<h1>{{ title }}</h1>` に変更
4. タイトル箇所に初期値が出力されているか確認 [変更箇所を確認する](https://github.com/kokushin/vue-hands-on/commit/055bbde54c4ea2dc655b1d12b1a10cd3f27dd935)
5. `methods` に `changeTitle` メソッドを追加
6. `this.title` の値を `Bar` に書き換え
7. ボタンをクリックしてタイトル箇所が Foo => Bar に変わるか確認 [変更箇所を確認する](https://github.com/kokushin/vue-hands-on/commit/ec9c0e54f71e9e0ce8627cf0205df5ae5bdb4174)

※ディレクティブは一部省略可能 → 例 `v-on:click` => `@click`, `v-bind:href` => `:href`

### 双方向バインディングを体験

1. `<template>` に `<input type="text" v-model="text">` を追加
2. `<p>{{ text }}</p>` を追加
3. `data` に `text` の初期値 `''` を設定
4. テキストフォームに文字を入力すると `<p>` の内容も書き換わることを確認

> [変更箇所を確認する](https://github.com/kokushin/vue-hands-on/commit/73ff1198dc3614b5e4adebee6d63c40ee768c3f8)

### 条件付きレンダリング（条件分岐） `v-if`

https://jp.vuejs.org/v2/guide/conditional.html

条件付きレンダリング `v-if`, `v-show` を利用すると、状態の変更に応じて動的に表示を切り替えることが可能

> [変更箇所を確認する](https://github.com/kokushin/vue-hands-on/commit/7aad22013d51dd068177cf3d5551ebbc9cfb6c8e)

### リストレンダリング（ループ処理） `v-for`

https://jp.vuejs.org/v2/guide/list.html

リストレンダリング `v-for` を利用すると、配列の要素分ループで出力させることが可能

> [変更箇所を確認する](https://github.com/kokushin/vue-hands-on/commit/5c7ed8b22f0fd42bf4a4cbe2f40c2d4039fd7d3a)

### コンポーネント間のデータ受け渡し方法など

http://www.webopixel.net/javascript/1224.html

`$emit`、`$parent` などを利用する

## 便利なツール・ライブラリ紹介

- Vue.js devtools https://goo.gl/GZyGZo
  - Vue.js用の開発者ツール
- Vuex https://vuex.vuejs.org/ja/intro.html
  - コンポーネント間のステート管理を楽にする
- Nuxt.js https://ja.nuxtjs.org/
  - SSR（サーバーサイドレンダリング）を簡単に行う
- Element http://element.eleme.io/#/
  - UIコンポーネントセット
- Onsen UI https://ja.onsen.io/vue/
  - UIコンポーネントセット（国産）
