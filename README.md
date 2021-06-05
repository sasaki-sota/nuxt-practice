# nuxt-practice

## ディレクトリ構成

**pages** **components** **assets** **static** **nuxt.config** **package.json**となっている

##### staticファイルは初めて

> static ディレクトリは直接サーバのルートに配置され、名前を保持しなければいけないファイル（例えば robots.txt）もしくは変更されない可能性の高いファイルが含まれています（例えば、favicon など）。

Reactの比較も含まれます。

### pages部分

**.tsx**から **.vue**に変わっただけ

### Link部分

**Link**から **NuxtLink**に変わっただけ

    <NuxtLink to="/">Home page</NuxtLink>

> サイト内の全てのページへのリンクに <NuxtLink> を使ってください。他のウェブサイトへのリンクがある場合は a タグを使ってください。

## CompositionAPIの利用方法

参考サイト： https://composition-api.nuxtjs.org/getting-started/setup

# TodoリストTips

### prevent

イベントのリロードを防ぐ

## defineComponent

参考サイト： https://qiita.com/ryo2132/items/f055679e9974dbc3f977  
型推論が聞くようにするもの  
setupメソッド内で**methods** **data** **ライフサイクル**を定義する。

## reactive

> 今までのdata()に相当するリアクティブなプロパティは、setup()内でref()またはreactive()で宣言します。

### pushメソッド

値を追加する  
参考サイト： https://qiita.com/_masa_u/items/f9076777b044673eea2a

### spliceメソッド

要素の変更  
`<配列>.splice(<始まりのインデックス>, <変更する要素数>, <変更後の要素>)`  
参考サイト： https://qiita.com/_masa_u/items/f9076777b044673eea2a

### toRefs

参考サイト： https://qiita.com/ryo2132/items/6dc51ede8082dea75812
> reactiveなオブジェクトの全てのプロパティをrefオブジェクトに変換したオブジェクトを返します。

#### returnの使い方

最後にreturnで関数などを記述しないと**template側で使用することができない**

## v-model

参考サイト： https://jp.vuejs.org/v2/guide/forms.html  
フォームの作成に必要

    <input v-model="searchText">
    下記のコードが上記のコードになっている
    <input :value="searchText" @input="searchText = $event.target.value">
