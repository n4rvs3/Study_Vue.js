# Vue.js

```js
var app = new Vue({
            el: "#app",
            data: {
                message: "Hello World"
            }
        });
```

`el` -> HTML要素のID指定
`data` -> データ(変数)の中身指定

Vueインスタンスの変数へアクセスする際は`this.変数名`

## 接頭詩 v-

`v-bind` -> HTML要素の属性を動的に設定できる
[分かりやすい記事](https://qiita.com/ota-meshi/items/ffa875daa9ebc9fc57c0)

`v-on` -> イベントリスナーを定義し、メソッドを呼び出すことが出来る

`v-if` -> 条件分岐の結果で要素の有無を指定できる

`v-once` -> Vueによるレンダリングを一度のみ実行する

`v-for` -> 配列制御ができる、利用する際は`v-bind:key`の指定が必須

`v-model` -> 状態管理のような物？入力された情報とデータの双方向バインディングが可能[サンプル](./cdn/model.html)

## 算術

`computed` -> 関数で処理したデータを返却するプロパティ。methodsとの違いは
<table>
    <tr>
        <th></th>
        <th>methods</th>
        <th>computed</th>
    </tr>
    <tr>
        <th>キャッシュされる？</th>
        <th>されない</th>
        <th>される</th>
    </tr>
    <tr>
        <th>引数</th>
        <th>使える</th>
        <th>使えない</th>
    </tr>
    <tr>
        <th>処理のタイミング</th>
        <th>呼び出し毎</th>
        <th>データ変更時</th>
    </tr>
</table>

<br />
<br />

# Vue-Cliを用いた開発

- `src/components`以下にコンポーネントファイルの配置
- 命名はキャメルケース(?)

## 基本構文

[サンプルファイル](./sample-app/src/components/SampleComponent.vue)

```vue
<template>
</template>

<script>
</script>

<style>
</style>
```

### propsのプロパティについて

`props`には3つのプロパティを指定できる

- type -> 型情報
- default -> 初期値
- required -> データ必須(nullを許容しない)

#### 指定できる型一覧
<table>
    <tr>
        <th>属性</th>
        <th>内容</th>
    </tr>
    <tr>
        <td>String</td>
        <td>文字列</td>
    </tr>
    <tr>
        <td>Number</td>
        <td>数値型</td>
    </tr>
    <tr>
        <td>Array</td>
        <td>配列型</td>
    </tr>
    <tr>
        <td>Boolean</td>
        <td>真偽値</td>
    </tr>
    <tr>
        <td>Object</td>
        <td>オブジェクト型</td>
    </tr>
    <tr>
        <td>Function</td>
        <td>関数</td>
    </tr>
    <tr>
        <td>Date</td>
        <td>日付</td>
    </tr>
    <tr>
        <td>null</td>
        <td>全て許容</td>
    </tr>
    <tr>
        <td>undefined</td>
        <td>全て許容</td>
    </tr>
</table>

# Nuxt.js

Vue.jsを用いて開発されているフレームワーク
SSR/SPA/SSG対応。
serverMiddlewareという機能を用いて簡単にBFFを導入できる
(WebAPIとか作れるイメージ)

## 環境構築

https://nuxtjs.org/docs/get-started/installation

`yarn create nuxt-app {アプリ名}`

上記を実行した際、数個の質問に解答する必要がある。内容はプロジェクトによって都度変更する(読めば分かる)

## ディレクトリ解説

```md
- root
    - .nuxt
        - 吐き出されたファイル。基本気にしなくて良い
    - components
        - ここにコンポーネントファイルを配置します。命名はキャメルケース
    - node_modules
        - モジュールディレクトリ
    - pages
        - ページファイルを配置できる。ルーティングはindex.vueを基準に各フォルダー、ページ名で自動的にルーティングしてくれる
    - static
        - 加工した画像やfavicon、ファイル名をそのまま利用したい場合はこちらに配置する。
    - store
        - https://nuxtjs.org/docs/directory-structure/store/ 公式の解説
        - https://noumenon-th.net/programming/2019/08/24/nuxt-js-store/ 分かりやすい記事
        - 状態管理用のディレクトリ
    - .editorconfig
    - .eslintcache
    - .eslintrc.js
        - eslintの設定ファイル
    - .gitignore
    - .prettierignore
    - .prettierrc
        - prettierの設定ファイル
    - jsconfig.json
        - コンパイルに関しての設定ファイル
    - nuxt.config.js
        - サイト全体の設定ファイル
    - package.json
    - README.md
    - yarn.lock
```