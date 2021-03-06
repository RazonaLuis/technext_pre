# CSS基礎

## 概要
CSSとは、Cascading Style Sheets（カスケーディング・スタイル・シート）の略で、  
HTMLで作成した文章を**装飾**するための言語です。  
主に、HTMLの各要素(タグで囲まれた部分)の  
**配置**、  
**サイズ**、  
**見た目(色など)**   
を決めます。

## 学ぶこと
このカリキュラムでは以下の内容を学びます。
- 書き方
- 構文
- 要素の構造

<!-- 
カリキュラムの内容の記述は必須ではありませんが、  
理解を深めるために、記述することを推奨しています。  

記述される場合は、`question/html_css/css_basic`フォルダを使用してください。  
HTMLは`index.html`に、CSSは`style.css`に記述してください。  
`index.html`をgoogle chromeにドラッグアンドドロップすることでブラウザでの確認は行えます。   -->


## 書き方
CSSの書き方は大きく分けて以下の3つがあります。
- インライン
- エンベッド
- 外部ファイル

まずは順番に紹介します。
CSSの構文(どのように見た目を変更するか)の詳細は後述するため、  
今は理解する必要はありません。

### インライン
インラインは、装飾したい要素のタグに直接CSSを書く方法です。  
`style="color: red;"`を以下の例のようにdivタグに追加してください。  
※colorは文字の色を変更するCSSです。  
<!-- 一番上の行の文字が赤くなるか確認してください。 -->

```html
  <div style="color: red;">CSS基礎</div>
  <div>CSS基礎</div>
  <div style="color: red;">CSS基礎</div>
  <div>CSS基礎</div>
```


### エンベッド
エンベッドは、HTMLのheadに`styleタグ`を追加して、  
そこにCSSを書く方法です。
<!-- 以下の例のようにhead内に`styleタグ`を追加してください。
※font-sizeは文字の大きさを変更するCSSです。
全ての文字が大きくなることを確認してください。 -->

```html
<head>
    <meta charset="UTF-8">
    <title>CSS_basic</title>
    <style>
        div {
            font-size: 50px;
        }
    </style>
</head>
```

### 外部ファイル
外部ファイルは、CSS用のファイルをHTMLとは別に作成する方法です。  
やることは大きく分けて2つです。  

① css用のファイルを作成  
② ①で作成したファイルをHTMLを記述してるファイルから読み込む  

まずは、①ですが、`index.html`が保存されているフォルダに`style.css`というファイルを作成します。  
※css用のファイルの拡張子(.の後ろ)は必ず`css`になります。
以下の内容を記述してください。
※background-colorは背景色を変更するCSSです。

```css
div {
    background-color: green;
}
```

次に②です。
①で作成したCSSをHTMLに反映させるために  
`index.html`の`head`内に、
`<link rel="stylesheet" href="style.css">`
を追記してください。
背景色が緑になっていることを確認してください。

```html
<head>
    <meta charset="UTF-8">
    <title>CSS_basic</title>
    <style>
        div {
            font-size: 50px;
        }
    </style>
    <link rel="stylesheet" href="style.css">
</head>
```

### どの書き方を使用するべきか
書き方を3つ紹介しましたが、基本的に使用する書き方は、
**外部ファイル**のみです。

なぜ外部ファイルのみになるかというと、  
①あとで変更するときに修正がしやすい(**保守性が高い**)  
②いろいろなページに使い回すことができる(**再利用性が高い**)  
③HTMLとCSSがそれぞれ別に書いてあるため読みやすい(**可読性が高い**)  
の3点で他の書き方と比較して優れているからです。

例えば、
①に関してですが、インラインで書いた場合ですが、  
見た目を変更したくなった場合、  
変更したいタグに書いてあるCSSを1つずつ全て修正する必要があります。(**保守性が低い**)  
今回の例のように2箇所だけであればいいですが、修正箇所が多くなってくると、  
修正漏れにも繋がります。

次に②に関してです。  
今回は1ページのみですが、通常Webサイトは複数ページから構成されることが多いです。  
企業のWebサイトであれば、TOPページと採用ページなどがあると思います。  
複数ページのWebサイトを作成する場合、ページの数だけHTMLファイルが必要になります。  
しかし、ページが異なっても共通して使えるCSSは非常に多いです。
外部ファイルを使用する場合、HTMLファイルからCSSを読み込むだけですみますが、  
インラインやエンベッドの場合、  
同じCSSでも、各HTMLに記述する必要があります。(**再利用性が低い**)   

上記のような理由から基本的に、外部ファイルを使用します。  
そのため、インラインや、エンベッドでの記述方法を覚える必要はありません。

## 構文
次にCSSの構文について説明します。
CSSの構文は以下の通りシンプルなものです。
```css
セレクタ {
    プロパティ: 値;
}
```

書式の意味としては、  
「 **どの要素の { 何を: どのようにする; }** 」  
というパターンで、行末にセミコロン（;）を書きます。  
また、「何を: どのようにする」という部分は必要に応じて複数追加できます。

![Overview](../img/css/how_to_write.png)

### 例
```
/* pタグの */
p {
  font-size: 20px;  /* フォントサイズを20pxにする */
  background-color: yellow;       /* 背景の色を黄色にする */
}
```
※/* */で囲まれている部分は**コメントアウト**といって、装飾とは関係ないメモになります。  


### セレクタとは
**セレクタ**の指定方法は非常に多くの方法があります。  
ここでは主要なものをいくつか紹介します。

|セレクタ       |説明      |書き方      |
|:--------------|:---------|:-----------|
|タグ           |HTMLのタグ|tag-name |
|id             |HTMLのタグに使用できる属性。<br>`<div id="id-name"></div>`の形で指定する。<br> idの名前は1つのHTMLファイル内で一意(重複しない)でなければいけない。 | #id-name|
|class          |HTMLのタグに使用できる属性。<br>タグに対して一つ、または複数の名前を設定します。<br>複数のタグに対しても、同じ名前を割り当てることができます。<br>複数の名前を一つのタグに割り当てる場合は、空白文字で区切ります。|.class-name|


もっとも使用されるセレクタは`class`です。  
セレクタに`class`を指定する場合は、
**class名の前に.(ドット)をつけます。**  
`class`を使用すると、classを追加、削除するだけで、  
後から簡単に装飾を変更することができます。
また、セレクタに`id`を指定する場合は、**id名の前に#をつけます。**  
タグの場合は、単純にタグの名称を記述します。  

例
```html
  <p>タグ</p>
  <div id="section"></div>
  <div class="btn"></div>
```

```css
/* pタグのfont-sizeを20pxにする */
p {
    font-size: 20px;
}

/* id名がsectionのタグのfont-sizeを20pxにする */
#section {
    font-size: 20px;
}

/* class名がbtnのタグのfont-sizeを20pxにする */
.btn {
    font-size: 20px;
}
```

ここでは詳しく紹介しませんが、  
`.section .btn`のように書くことで、  
sectionクラスの中のbtnクラス、といったような細かい指定も可能です。

興味がある方は以下のリンクを参考にしてください。

#### 参考リンク
- [CSS セレクタ](https://developer.mozilla.org/ja/docs/Web/CSS/CSS_Selectors)
- [セレクタの種類](http://www.htmq.com/csskihon/005.shtml)

#### セレクタの優先順位
例えば以下の例のように  
**同じ要素**の  
**同じプロパティ**に  
**異なる値**が指定されることがあります。  

例
```html
  <div class="test">テキスト</div>
```

```css
div {
    font-size: 20px;
}

.test {
    font-size: 50px;
}
```

セレクタの種類が同じ場合、**後から指定したスタイルが適用**されますが、  
種類の異なるセレクタによって同じプロパティが指定された場合、  
規則に従って優先順位が決定されます。  
規則は非常に細かいですが、特に覚える必要はありません。  
大まかなに**具体的に指定してるセレクタが優先される**程度の理解で問題ありません。


### プロパティと値
**プロパティ**とは適用するスタイルの種類のことで、   
**値**にはそのプロパティごとに用意されたものを必要に応じて記述します。

例えば、文字の色を変更するプロパティ、`color`に`green`という値を与えるなどです。


## 要素の構造
要素の構造は、次のようになっています。

![コンテンツの構造](../img/css/structure.png)

以下のボタンの例でいうと、  
「出席」、「学習スタート」という文字が`コンテンツ`  
黒い線が`border`  
「出席」と黒い線の間が`padding`  
「出席ボタン」と「学習スタートボタン」の間が`margin`となります。  
![ボタン](../img/css/btn.png)

marginやpaddingは以下のように指定できます。

### marginの指定について
* margin （値）
    * 上下左右の４方向について、すべて同じマージンを指定する
* margin（上）（右）（下）（左）
    * 上下左右のマージンをそれぞれ別に指定する  
      例：`margin: 10px 5px 10px 5px;`

### paddingの指定について
* padding（値）
    * 上下左右の４方向について、すべて同じ余白を指定する
* padding（上）（右）（下）（左）
    * 上下左右の余白をそれぞれ別に指定する  
      例：`padding: 10px 5px 10px 5px;`


## 参考サイト
CSSにどのようなプロパティがあるか以下のサイトで調べて、  
使ってみましょう。

- [CSSリファレンス | MDN](https://developer.mozilla.org/ja/docs/Web/CSS/Reference)
- [CSSリファレンス | クイックリファレンス](http://www.htmq.com/css3/)

## 次の単元へ
次に進むには下記のリンクを押してください。<br>
https://github.com/RazonaLuis/technext_pre/blob/main/02_html_css/03_flexbox.md
