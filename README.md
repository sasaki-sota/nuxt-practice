# nuxt-practice
##実務想定でのやりたい技術スタック

    dockerで環境構築
    vueでの記述はcompositionAPI?というものを使って関数ベースで実装（React-hooksのような感じ）
    記述自体はtypeScriptベース
    APIクライアントのGraphQLを使ってデータを実際に取得してみる
    (APIは自分で作成できればより良い)
    デザインは最近ハマっているTailwindCSSで

## ディレクトリ構成
**pages** **components** **assets** **static** **nuxt.config** **package.json**となっている  
##### staticファイルは初めて  
>static  ディレクトリは直接サーバのルートに配置され、名前を保持しなければいけないファイル（例えば robots.txt）もしくは変更されない可能性の高いファイルが含まれています（例えば、favicon など）。

Reactの比較も含まれます。

### pages部分
**.tsx**から **.vue**に変わっただけ

### Link部分
**Link**から **NuxtLink**に変わっただけ

    <NuxtLink to="/">Home page</NuxtLink>
> サイト内の全てのページへのリンクに <NuxtLink> を使ってください。他のウェブサイトへのリンクがある場合は <a> タグを使ってください。

