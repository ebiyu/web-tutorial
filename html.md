# HTML編

[要望](https://github.com/ebiyuu1121/web-tutorial/issues/new/choose) / [編集を提案](https://github.com/ebiyuu1121/web-tutorial/edit/main/html.md)

高機能なウェブページを作るには、最低限、以下の 3 つの言語を使うことが必要です。

| 言語           | 役割                                                                                                           | 備考                 |
| :------------- | :------------------------------------------------------------------------------------------------------------- | :------------------- |
| **HTML**       | ウェブページの構造を記述する。                                                                                 | この項目で解説します |
| **CSS**        | ウェブページの各構成要素の見た目を設定する。                                                                   |                      |
| **JavaScript** | ユーザーの入力を受け取った処理に応じて表示を変える、サーバーからのデータを受け取るなどの動的な処理を実現する。 |                      |

表を見ると分かるように、これら 3 つの言語にはそれぞれ固有の役割があります。ボタンを配置したり、文章を表示させたり、枠を配置したりするのは HTML の仕事です。ボタンや枠などの構成要素の具体的な見た目（色、枠線の太さ、文字の大きさなど）を設定するのは CSS の仕事です。クリックすると枠が現れたり、お知らせの内容を動的に変えたりといったことを行うのは JavaScript の仕事です。これらが分業し、協力することでウェブページができています。

## 章末課題

1. git 編でクローンした練習用リポジトリに、`practice.html`というファイルを作成しましょう。
2. 写真のような web サイトを、html を使って書いてみましょう。
   ![](imgs/html-question.png)
3. git 編でやったように、ステージ・コミット・push をして反映させましょう。

## HTML とは

**HTML**（HyperText Markup Language）とは、ウェブページを記述するためのプログラム言語（？？？「プログラム言語じゃなくてマークアップ言語なんだよなあ〜〜〜＾」）です。上で説明したように、HTML が担当するのは、ウェブページの構造を記述する部分です。どの順番でどんな構成要素を配置するかを設定します。

余談ですが、HTML は構造を指定する以外に構成要素の見た目を設定することもできます。ただし、それは昔の悪い風習であり、現在ではその仕事は CSS に任せるのがよいとされています。

## HTML の記述

HTML の内容はすべて HTML ファイル（拡張子`.html`）に記述します。HTML ファイルはブラウザで開くことができ、開くと記述した内容のウェブページが表示されます。

まずは，標準的な HTML ファイルの内容を見てみましょう。これを見れば、基本的な書き方や文法が身につくでしょう。

```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="UTF-8" />
    <title>ウェブサイトのタイトル</title>
  </head>
  <body>
    （ここに内容が入ります）
  </body>
</html>
```

まずは上の内容をコピペして`index.html`という名前のファイルを作成し、好きなブラウザで開いてみましょう。
「（ここに内容が入ります）」という文字列が表示されれば成功です。

## HTML の文法の基礎

### タグ

基本的に、HTML において、構成要素は**タグ**とよばれる記号を使って記述します。例えば、`hoge`という名前のタグは、`<hoge> ... </hoge>`のように書きます（`...`には構成要素の中身が入ります）。それぞれのタグには種類ごとに異なる機能を持っています。上に出てきたタグは次のような意味を持ちます。

| タグ      | 役割                                                                           |
| :-------- | :----------------------------------------------------------------------------- |
| `<html>`  | この中に HTML の内容が入るよという意味です。                                   |
| `<head>`  | この中にウェブページの基本情報を書きます。表示はされません。                   |
| `<title>` | この中にウェブページのタイトルを書きます。ブラウザのタブに表示されるやつです。 |
| `<body>`  | この中にウェブページの中身を書きます。ブラウザに表示される部分（本体）です。   |
| `<meta>`  | 各種設定を書きます。初めのうちは気にしなくていいです。                         |

基本的に、ウェブページに表示される部分（中身）は`<body>`タグの中に記述します。というわけで、初めのうちは`<body>`の外に記述する文言はコピペでいいと思います。

### おもな構成要素の記述方法

`<body>`タグの中には、ウェブページの中に表示したいさまざまな構成要素を記述する必要があります。まずは、主な構成要素とそのタグを概観しましょう。

| タグ          | 役割                                                                                                                                                                                                                                            |
| :------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `<div>`       | 仮想的な枠（ブロック）を表します。表示させたいパーツをまとめたグループのようなものです。めちゃくちゃ使います。このタグを付けなくても見た目の変化はほとんどありませんが、後ほど CSS を使ってスタイルを付けていく際に使うのでつけておきましょう。 |
| `<h1>`~`<h6>` | 見出しを表わします。数字が小大きいほど見出しが小さくなります。（h1 は大見出し、h2 は小見出し...など）                                                                                                                                           |
| `<p>`         | 文章の段落のまとまりを表します。                                                                                                                                                                                                                |
| `<a>`         | 行の一部分に対して、ハイパーリンクを設定します。                                                                                                                                                                                                |
| `<img>`       | 画像を表示します。                                                                                                                                                                                                                              |
| `<span>`      | 行の一部分に対して、何らかのまとまりであることを意味します。このタグを付けなくても見た目の変化はありませんが、後ほど CSS を学ぶときに使います。                                                                                                 |

```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="UTF-8" />
    <title>ウェブサイトのタイトル</title>
  </head>
  <body>
    <h1>見出し！</h1>
    <div>
      <p>
        1段落目です。ここに文章を入力します。ここに文章を入力します。ここに文章を入力します。
      </p>
      <p>
        2段落目です。ここに文章を入力します。ここに文章を入力します。ここに文章を入力します。
      </p>
    </div>
  </body>
</html>
```

これを保存してブラウザで開いてみましょう。HTML だけではまだスタイルが設定されていないため味気ないですが、`<div>`タグによって構成要素のまとまりが指定されていることを確認しましょう。

### 属性

タグには、**属性**と呼ばれる詳細設定（プロパティのようなもの）を記述することができます。例えば、`<hoge>`タグの`attr`属性の値を`val`にするには`<hoge attr="val">`のように書きます。

属性を指定することが多いタグの代表格は、リンクを意味する`<a>`タグです。`<a>`タグには`href`という属性があり、その値にリンク先の URL を設定することができます。例えば、`https://www.google.co.jp`へのリンクを設定するには

```html
<a href="https://www.google.co.jp">Googleへのリンク</a>
```

のように書きます。

タグにどんな属性を設定できるかは、そのタグの種類によって異なります。例えば、`div`タグに`href`という属性はありません。

### ブロック要素とインライン要素

（なんか書く）

### 書ききれなかったこと

- 画像の表示
- リストの表示

### もっと詳しく知るには

- ググる
- 詳しい人に聞く
- チュートリアルをやってみる
- 公式ドキュメントを読む

### これが読めたら免許皆伝

[阿部寛のホームページ](http://abehiroshi.la.coocan.jp/top.htm)を記述する HTML が読めれば OK です！ ブラウザ上で表示しているウェブページを記述する HTML の中身（これを**ソースコード**といいます）は、右クリック＞「ソースの表示」で確認できます。

```html
<html>
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=Shift_JIS" />
    <meta http-equiv="Content-Style-Type" content="text/css" />
    <meta
      name="GENERATOR"
      content="JustSystems Homepage Builder Version 20.0.6.0 for Windows"
    />
    <title>阿部 寛のホームページ</title>
  </head>
  <body background="image/abehiroshi.jpg">
    <br />
    <h1 align="center">阿部 寛のホームページ</h1>
    <table align="center">
      <tr>
        <td rowspan="2">
          <img
            src="abe-top-20190328-2.jpg"
            width="350"
            height="414"
            border="0"
          /><br />
          <br />
          <table width="256">
            <tr>
              <td width="14">&nbsp;</td>
              <td width="230">阿部 寛（あべ ひろし）<br /></td>
            </tr>
            <tr>
              <td>&nbsp;</td>
              <td>生年月日 1964年6月22日<br /></td>
            </tr>
            <tr>
              <td>&nbsp;</td>
              <td>血液型 A型<br /></td>
            </tr>
            <tr>
              <td>&nbsp;</td>
              <td><a href="prof/prof.htm">プロフィール</a></td>
            </tr>
            <tr>
              <td>&nbsp;</td>
              <td>&nbsp;</td>
            </tr>
            <tr>
              <td colspan="2">
                <br />
                If you have any enquiries regarding my TV drama or film, or
                would like to make an enquiry concerning future projects, please
                do not hesitate to contact me through the following email
                address.<br />
                <br />
                mail:<a href="mailto:shigeta@navy.plala.or.jp"
                  >shigeta@navy.plala.or.jp</a
                >
              </td>
            </tr>
          </table>
          <br />
          所属<strong>:</strong><br />
          茂田オフィス<br />
          107-0052<br />
          東京都港区赤坂9-5-29 <br />
          赤坂ロイヤルマンション303<br />

          TEL : +81-3-5410-8585<br />
          FAX : +81-3-5410-0588
        </td>
        <td>&nbsp;</td>
        <td><div align="center">★★★　最新情報　★★★</div></td>
      </tr>
      <tr>
        <td></td>
        <td>
          <table width="100%" border="0" cellspacing="0" cellpadding="0">
            <tr>
              <td align="left" valign="bottom"><hr width="100%" size="1" /></td>
            </tr>
          </table>
          <!-- start　-->
          <table width="100%" border="0" cellspacing="0" cellpadding="0">
            <tr>
              <td align="left" valign="top"><strong>・ドラマ</strong></td>
            </tr>
          </table>
          <table border="0" cellspacing="5" cellpadding="0">
            <tr>
              <td width="70" align="left" valign="top">&nbsp;</td>
              <td>
                <strong>
                  <a href="https://www.tbs.co.jp/dragonzakura/" target="_blank"
                    >「ドラゴン桜2」</a
                  >(仮)<font color="#ff0000"></font><br />
                  <font color="#ff0000"
                    >2020年夏を予定しておりましたが、新型コロナウイルス感染拡大の影響により放送延期を決定いたしました。</font
                  ></strong
                >
              </td>
            </tr>
          </table>
          <!-- end　-->
          <!-- start　-->
          <table width="100%" border="0" cellspacing="0" cellpadding="0">
            <tr>
              <td align="left" valign="bottom"><hr width="100%" size="1" /></td>
            </tr>
          </table>

          <table width="100%" border="0" cellspacing="0" cellpadding="0">
            <tr>
              <td align="left" valign="top"><strong>・映画</strong></td>
            </tr>
          </table>
          <table border="0" cellspacing="5" cellpadding="0">
            <tr>
              <td width="70" align="left" valign="top">&nbsp;</td>
              <td>
                <strong
                  >「護られなかった者たちへ」 <br />
                  2021年公開予定<br />
                </strong>
              </td>
            </tr>
          </table>
          <table border="0" cellspacing="5" cellpadding="0">
            <tr>
              <td width="70" align="left" valign="top">&nbsp;</td>
              <td>
                <strong
                  ><br />
                  <a href="http://www.hokusai2020.com/" target="_blank"
                    >「HOKUSAI」</a
                  >
                  <br />
                  2021年 公開予定<br />
                  <font color="#ff0000">※公開が延期になりました。</font><br />
                </strong>
              </td>
            </tr>
          </table>
          <table border="0" cellspacing="5" cellpadding="0">
            <tr>
              <td width="70" align="left" valign="top"></td>
              <td></td>
            </tr>
          </table>
          <!-- end　-->

          <table width="100%" border="0" cellspacing="0" cellpadding="0">
            <tr>
              <td align="left" valign="bottom"><hr width="100%" size="1" /></td>
            </tr>
          </table>
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
        </td>
      </tr>
    </table>
  </body>
</html>
```

なお、阿部寛のホームページは大昔に作られたため、現在の観点からみると良くない書き方が多くみられます。参考にはしないでね。
わからないタグや属性・記法があったらググろう！

## 章末課題

1. git 編でクローンした練習用リポジトリに、`practice.html`というファイルを作成しましょう。
2. 写真のような web サイトを、html を使って書いてみましょう。
   ![](imgs/html-question.png)
3. git 編でやったように、ステージ・コミット・push をして反映させましょう。

## 次回予告

HTML を使って記述したウェブページをブラウザで表示させても、無味乾燥で味気ないですよね？ HTML は構造を扱う言語なので、構成要素を配置するのが仕事であって、見た目に関しては関知しないからです。各構成要素の見た目をいじって見栄えを良くするのは CSS の仕事です。

次は[CSS 編](css.md)！
