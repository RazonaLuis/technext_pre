# Webサイト作成チャレンジ

## ゴール
Webサイトを見たときにHTMLの構造を考えることができる
Webサイト作成の流れを理解している。

## 概要
このカリキュラムでは今まで勉強してきたことの集大成として Webサイトの作成を行います。

実践的なwebサイトの作成を通して、今まで学んできた内容の定着をはかります。

作成するWebサイトの見本は以下のimgフォルダーに入っています。<br>
pre-master/question/html_css/welcome_to_technext/img/welcome_to_technext.png

わからない部分は今までのカリキュラムを見返したり、 Google検索などしてみてください。

また、本課題のゴールは上述の通りのため、 細かい文字のサイズや色などの正確さは異なっても問題ありません。
加えて、HTMLのタグも数種類使用してますが、実現方法は様々なので、
タグがサンプルと違っても問題ありません。

完成したら画像やフォントのサイズ、文字の色、 各コンテンツのレイアウトなどを変更して、
オリジナルのWebサイト作成にも挑戦してみてください！

コーディングはquestion/welcome_technextフォルダを使用して、
HTMLはindex.htmlに、CSSはstyle.cssに記述してください。 index.htmlをgoogle chromeにドラッグアンドドロップすることでブラウザでの確認を行えます。

こちらをクリックしてください

## 作成の流れ(概要)
いきなり作成してくださいとなってもできないのは当たり前なので、 まずは大まかな流れを説明します。

1. Webサイト全体のHTMLの構造を確認してHTMLを記述する
2. 作成する場所を決める
3. 2で決めた箇所のHTMLの構造を確認してHTMLを記述する
4. 3で記述したHTMLにCSSをつけるためのクラスを記述する
5. 2で決めた場所のどこをCSSで装飾するか決める
6. CSSを記述する
7. 6で記述した通りになっているかブラウザで確認する
8. (7で想定通りでない場合のみ)Developer toolなどを使用して原因の確認
9. 5に戻ってCSSを記述

CSSが全て記述できたら、 上記2に戻って新しい箇所の作成に移ります。
この手順を繰り返してWebサイトを作成します。

### HTMLの構造に関して
HTMLの構造とは、どのようにタグが組まれているかということになります。
次の作成の流れ(具体例) で実際に作成するWebサイトを例に説明します。

### CSSの記述に関して
CSSで決めることは主に以下の3つです。

1. 要素の配置
2. 要素のサイズ(font-size, heightなど)
3. 要素の見た目(colorなど)

※要素とはHTMLのあるタグの始まりから終わりまでです。

### 配置に関して
配置を決めるのは、要素の並び順と隙間です。 配置を決めるプロパティは複数ありますが、
今回のサンプルではFlexboxを使用しています。

もちろん他のプロパティを使用していただいても構いませんが、
配置の指定が、サイズや見た目と比較すると難易度が高いため、
比較的簡単に使用できるFlexboxがおすすめです。

## 作成の流れ(具体例)
### Webサイト全体のHTMLの構造を確認してHTMLを記述する
まずはWebサイト全体のHTMLの構造を確認です。
今回のWebサイトの場合、
①header(画面最上部水色の部分)
②Welcome to TechNext
③programming
④English
⑤footer(画面最下部紺色の部分)
の5つの部品から構成されています。

HTMLのbodyタグは以下のような構造です。
※で囲んでいる部分はコメントアウトといって、 プログラムとは関係ないメモになります。
```html
<body>
    <!-- header -->
    <div></div>

     <!-- welcome -->
    <div></div>

    <!-- programming -->
    <div></div>

    <!-- English -->
    <div></div>

    <!-- footer -->
    <div></div>

</body>
```

### headerのHTMLの構造を確認してHTMLを記述する
今回は①headerから作成します。
headerは
左側のブロックと右側のブロックに分けることができます。
左側のブロックは画像とTechNextという文字の2つ
右側のブロックはPROGRAMMINGとENGLISHという文字の 2つに分けることができます。

そのため以下のような構造になります。
```html
 <!-- header -->
 <div>
     <!-- header左側 -->
     <div>
         <img src="img/seedkun.png" alt="">
         <span>TechNext</span>
     </div>

     <!-- header右側 -->
     <div>
         <div>PROGRAMMING</div>
         <div>ENGLISH</div>
     </div>
 </div>
```
このようにWebサイトがどんな構造になっているか 理解することでHTMLが書きやすくなります。

### クラスをつける
HTMLの記述ができたので、CSSをつけるためにクラスをつけます。
この時点で、どこにクラスをつけるか、 名前はどうすれば良いかなど迷うかもしれませんが、
あとで追加、修正、削除など簡単にできるので、
おそらく必要と思われる場所につけていただければ問題ありません。

```html
<div class="header">
  <!-- header左側 -->
  <div class="header-left">
      <img src="img/seedkun.png" alt="">
      <span class="name">TechNext</span>
  </div>

  <!-- header右側 -->
  <div class="header-right">
      <div>HTML&CSS</div>
      <div>Javascript</div>
  </div>
</div>
```

### CSSを記述する
クラスをつけることができたので、 次はCSSを記述してレイアウトを整えていきます。
コツは、まとめて複数のことはせず、1つ1つやることです。
今回は、フォントの色、画像のサイズ、背景の色など複数修正する必要が
ありますが、まとめて実施すると間違えたとき に原因の特定が難しくなります。
例えば、

1. 画像のサイズを変更することを決める
2. 画像のサイズを変更するCSSを記述する
3. 2が反映されていることを確認する
4. 背景色を変更することを決める
5. 背景色を変更するCSSを記述する
6. 5が反映されていることを確認する といった流れです。

### 画像のサイズを変更する
画像はheder-left クラスの中のimgタグなので、
セレクタは.header-left imgとなります。
サイズを変更しますが、画像の場合、高さ、または幅のどちらか一方を指定すると、
もう一方の値が自動で決まります。今回は高さを指定します。
そのためプロパティはheightです。
```css
.header-left img {
    height: 60px;
}
```
### 背景色を変更する
headerの背景色を変更したいので、
セレクタは.headerとなります。
プロパティはbackground-colorです。
```css
.header {
  background-color: #1dace0;
}
```
### headerの要素を横並びにする
header-leftクラスとheader-rightクラスを横並びにしたいので、
セレクタは.header、プロパティはdisplay:flexとなります。
※Flexboxで要素を横並びにする場合、横並びにしたい要素の親要素にdisplay:flexをつけます。
```css
.header {
  background-color: #1dace0;
  display: flex;
}
```

### headerの要素を両端によせる
header-leftクラスとheader-rightクラスが 横並びになりましたが、
左よせになってるため、左右に離すためにjustify-content: space-betweenを使用します。

```css
.header {
  background-color: #1dace0;
  display: flex;
  justify-content: space-between;  
}
```

### headerの両端に隙間をあける
header-leftクラスとheader-rightクラスの間に隙間があきましたが、
それぞれの外側の隙間がなくなってしまったので、headerクラスにpaddingをつけます。
```css
.header {
  background-color: #1dace0;
  display: flex;
  justify-content: space-between;
  padding: 0 80px;
}
```
上記のような流れで1つずつ試していきます。
わからない部分は回答例を確認しながら書いていただければ問題ありません。

以下にheader部分に使用したCSSを全て記述してます。
```css
/* header */
.header {
  display: flex;
  justify-content: space-between;
  background-color: #1dace0;
  color: #fff;
  font-size: 18px;
  padding: 5px 0;
}

.header-left {
  display: flex;
  align-items: center;
  margin-left: 80px;
}

.header-left img {
  height: 60px;
}

.header-left .name {
  color: #eae51f;
}

.header-right {
  display: flex;
  align-items: center;
  margin-right: 80px;
}

.header-right div {
  padding: 0 20px;
}
/* headerここまで */
```
ここまでで、headerの作成が終わりです。
1つ目のブロックが終わったので、次のブロックも同じ流れで書いてみましょう。

## 補足

### 使用してる主なCSSプロパティ
- display: flex
- justify-content:
- align-items:
- flex-direction:
- height: 100vh;
- nth-child(first-child)

### 使用してるカラーコード
CSSでは色の指定をする方法が複数あり、
ここでは16進数という英数字を使用するやり方で色を指定してます。

- headerの背景の水色: #1dace0
- headerの黄色の文字: #eae51f
- 白い文字: #fff
- 灰色の文字: #ddd
- footerの紺色の背景: #233f51

### 参考リンク
色 | MDN
https://developer.mozilla.org/ja/docs/Web/CSS/CSS_Colors/Color_picker_tool

### 回答
回答となるフォルダはanswer/welcome_technext です。
必要に応じて確認してください。

## チェック表
下記のリンクをクリックして質問にお答えください。<br>
https://docs.google.com/forms/d/e/1FAIpQLSc7u7r8CPdtr1mAIbaTtOJv-ECQRNzlLe1vFH1W53Gr2xaQBA/viewform?usp=sf_link

## 次の単元へ
次に進むには下記のリンクを押してください。<br>
https://github.com/RazonaLuis/technext_pre/blob/main/03_javascript/01_JavaScript%E3%81%A8%E3%81%AF.md