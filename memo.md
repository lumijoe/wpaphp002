**A:ディレクトリの作成**

## ディレクトリを作成するとき

・デザインデータの URL などを管理できるウ rl ディレクトリを作成
URL.txt というファイルを作成し URL 管理すると開発効率が良い！

**B:body までのテンプレートの利用**

## body>div>

body
トップページ：class も id も home

**C:レイアウト構成/main の中身の構成/header の中身の構成**

## 1 大きな構成：　 5 つ class/id

header,main,footer,スマホメニュー,ハンバーガーボタン

1 header l-hd header
2 main l-main main_area
3 footer l-ft footer
4 div l-sp-menu sp_menu
5 div l-sp-menu-btn sp_menu_btn

## 2 main の構成：　 5 つ class/id

first ビュー、メッセージ、オーナーや人、店舗情報、予約情報

1 header l-hd header
2 main l-main main_area
///2-1 l-home-firstview firstview
///2-2 l-section message
///2-3 l-section owner-person
///2-4 l-section shop-info
///2-5 l-section reserve-info  
3 footer l-ft footer
4 div l-sp-menu sp_menu
5 div l-sp-menu-btn sp_menu_btn

## developer tool は responsive の 75%が使いやすい

1600x3000 くらいのものと併用すると使いやすい

**D:header の作り込み/スタイル**

## 3 header の構成　：2 つ　

ロゴ、ナビゲーション
( \_ \_ は続けると md ではエラーが出るので半角スペースで処理している)

1 header l-hd header
///1-1 p-hd
/// 1-1-1 p-hd\_ _logo
/// 1-1-2 p-hd_ \_nav header_nav
2 main l-main main_area
///2-1 l-home-firstview firstview
///2-2 l-section message
///2-3 l-section owner-person
///2-4 l-section shop-info
///2-5 l-section reserve-info  
3 footer l-ft footer
4 div l-sp-menu sp_menu
5 div l-sp-menu-btn sp_menu_btn

## header ロゴと文字サイズの最適化　最小、推奨、最大

&\_\_logo img {
// max-width: 100%;
width: clamp(220px, 100%, 430px);
}

## フォント種類

$fontMeiryo: "メイリオ", Meiryo, Osaka, "ＭＳ Ｐゴシック", "MS PGothic", Arial,
  sans-serif;
$fontHira: "ヒラギノ角ゴ Pro W3", "Hiragino Kaku Gothic Pro", "メイリオ", Meiryo,
Osaka, "ＭＳ Ｐゴシック", "MS PGothic", sans-serif;
$fontMintyo: "ＭＳ Ｐ明朝", "MS PMincho", "ヒラギノ明朝 Pro W3",
  "Hiragino Mincho Pro", serif;
$fontGothic: "ＭＳ Ｐゴシック", "MS PGothic", sans-serif;
$fontRaleway: "Raleway", "MS PGothic", sans-serif;
$fontNoto: "Noto Sans Japanese", serif;
$fontLato: "Lato", "arial", sans-serif;
$fontOpenSans: "Open Sans", Arial, sans-serif;
$fontYuMin: "游明朝体", "Yu Mincho", YuMincho, "ヒラギノ明朝 Pro",
  "Hiragino Mincho Pro", "MS P明朝", "MS PMincho", serif;
$fontYuGothic: "游ゴシック体", YuGothic, "游ゴシック", "Yu Gothic", "メイリオ",
sans-serif;
$fontNoteMin: "ヒラギノ明朝 Pro W3", "Hiragino Mincho Pro", "HiraMinProN-W3",
  "Noto Serif JP", "游明朝", "Yu Mincho", "游明朝体", "YuMincho", "HGS明朝E",
  serif;
$roboto: "Roboto Condensed", sans-serif;

## フォントを link タグでも css に import でも良い（wordpress）の場合

<style>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@100..900&display=swap');
</style>でも良いが、linkの方が読み込みが早いのでlinkで作成して

wordpress の場合は functions.php に変換して記述する方が良い

## 3-a 画像 firstview の設定は picture タグで

## picture タグとして使用するとき

・767 以下スマホの時、768 以上パソコンの時、どちらにも合わない時などが設定できる

## image として使用するとき

・画像は div や section タグで挟むと途端にサイズはみ出るので img 自体に max-width100%(親要素サイズに対して)の指定が必要

## background として使用するとき

・背景では background-size：cover;の指定が必要

## 最初から img { max-width :100%;}の方がいいのか？

html で img max-width 100%にしたらどう？未検証

## 3-b ページ内リンク設定　　 home へ

ジャンプ：ページ内の異なる箇所へ移動
遷移：異なるページへ移動

## 3-c スタイル設置　

## assets/scss/\_setting.scss のファイルを作成

その中に
・カラー　＄ siteOrange: #**\_\_**
・フォント .c-h2--65-0-121 {
// 調整(XD65→63,0,121/58em)
font-size: 63px;
letter-spacing: 0px;
line-height: 2.08em;
}
・余白
.c-padding--x50px {
padding-left: 50px;
padding-right: 50px;
}
.c-padding--y100px {
padding-top: 100px;
padding-bottom: 100px;
}
.c-margin--0auto {
margin: 0 auto;
}
とかを一旦指定してしまうこと！

これはうまくいかなかったので next で処理した
・sass フォルダをルート直下に作成
・その中に\_common_first_view.scss ファイルを作成
・root/sass/\_common_first_view.scss を作成しコードを記述
・sass ファイルに css を記述したら,watch sass をクリックして watching にしてコンパイルする
next
・css フォルダの中に\_common_first_view.scss ファイルを作成、コードを書いてコンパイル
・Generated:
/Users/lumi/Desktop/u_pra01_ummeccha/css/home_first_view.css.map
/Users/lumi/Desktop/u_pra01_ummeccha/css/home_first_view.css 出来上がった

## nav 作成

・li>a でリンクさせる
・main 内の id を利用して navlist に ahref でジャンプさせる
・\_setting.scss で作っている$siteColor を利用する
　\_common_first_view.scss ファイルの中で\_setting.scss の設定を使用する方法は、\_common_first_view.scss ファイル先頭に、@use "setting" as \*;を記述することで利用できるようになる。カラーを変数で利用している Next.js のコンポーネントのような使い方

## 4 ナビ作成 下線　ハイライト　外線

a タグのメニューテキストを hover したら下線が引かれるようにする
・下線は a タグには指定せず、a タグの中に span を入れてそこに下線を指定すると、テキストピッタリに下線がひかれ余白もきちんと開く設定が可能
・これでもいける半分を半透明にして
.p-item-faq {  
 &--question {
font-size: 25px;
line-height: 1.69em;
color: $siteGreen;
font-weight: bold;
&-text {
background: linear-gradient(to bottom, rgb(255, 255, 217, 0) 65%, rgb(255, 255, 217, 0.57) 35%);
} ##　５背景とロゴ
背景とロゴを合わせた全体枠
・100vw、100vh と指定する
・のなかのコンテンツ source は w100%,h100%
・ロゴは大きさが大体アートボード 1600 に対して 600px ぐらいなので
レスポンシブを実現させるには、600/1600 として 37％ぐらいと率でサイズを指定しておく

## 使いまわせる要素は c-

各セクションのタイトルは同じ文字サイズで色も同じなので使いまわせると判断し、c-を使用する
・c-width は、セクションの幅
・c-section-title は、セクションのタイトル

## 7 レスポンシブ対応可能にする c-width

中のコンテンツがデザインデータでは中央に横幅 840px で存在しているけれど
そのまま 840px にするとデバイスサイズ 840px に時に左右の余白がなくなってしまい、キチキチのサイズになってしまうので、
margin 0 auto,
padding 0 50px,
max-width 940px を指定するとよい
かつ、
・p-section を padding 0 50px／c-width を max-width940px と margin0auto に分けると良い
・コンテンツサイズを max-width940 と margin0 auto にして
・余白指定を 0 50px のように別で指定すると、
レイアウトが横幅いっぱいに指定されるセクションと
余白３０％とか 50px とかのように余白サイズが違うセクションを簡単に存在させることができる
セクションごとに余白サイズが違う時の指定の仕方
１：Padding だけのクラスを設定する
２：marign と横幅を指定したクラスを設定する
で、セクションごとに 2 と 1 のサイズを決めて組み合わせて 1 つのセクションと余白をセットでニコイチで完成させるとレイアウト組がしやすい

<section class="l-section" id="message">
                <!-- 7　レスポンシブ対応できるc-width -->
                <div class="p-section c-width">
                    <h2 class="c-section-title">日本海の恵み<br> 佐渡の海鮮料理でおもてなし</h2>
                    <div class="p-message-text">
                        <p class="c-section-text">
                            テキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキスト
                        </p>
                    </div>
                </div>
            </section>
            <section class="l-section" id="message">
                <!-- 7　レスポンシブ対応できるc-width -->
                <div class="p-section c-width2">
                    <h2 class="c-section-title">日本海の恵み<br> 佐渡の海鮮料理でおもてなし</h2>
                    <div class="p-message-text">
                        <p class="c-section-text">
                           テキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキスト
                        </p>
                    </div>
                </div>
            </section>
scss設計
.c-width {
  max-width: 940px;
  margin: 0 auto;
}
.c-width2 {
  max-width: 600px;
  margin: 0 auto;
}

## 行間と文字間

行間 line-height1.5
XD 行サイズ 60/テキストサイズ 40px=60/40=1.5

文字間 letter-spacing0.1
XD 文字間 AV4px/テキストサイズ 40px=4/40=0.1

XD で横 AV が 1.5px という表示になっていたら文字間 1.5 ということ
文字のサイズ 15px となっていたらサイズ 15px ということ
letter-spacing の em は、文字間 ÷ サイズになるので
1.5÷15 として=0.1em となる

## 8 grid

横に何枚並べるかの指定
１列目が１枚、２列目が２枚、３列目が１枚の場合
一番多い数字に合わせて、１枚の部分は結合するイメージで。

## icon

FontAwasome
https://fontawesome.com/search?q=calender&o=r
circle-user https://fontawesome.com/search?q=user%20circle&o=r

## svg ファイル処理

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">⭐️<!--!Font Awesome Free 6.5.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.-->⭐️<path d="M48 64C21.5 64 0 85.5 0 112c0 15.1 7.1 29.3 19.2 38.4L236.8 313.6c11.4 8.5 27 8.5 38.4 0L492.8 150.4c12.1-9.1 19.2-23.3 19.2-38.4c0-26.5-21.5-48-48-48H48zM0 176V384c0 35.3 28.7 64 64 64H448c35.3 0 64-28.7 64-64V176L294.4 339.2c-22.8 17.1-54 17.1-76.8 0L0 176z"/></svg>

となっているので、⭐️ から ⭐️ の間を削除し<path>を入れ子にする
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M48 64C21.5 64 0 85.5 0 112c0 15.1 7.1 29.3 19.2 38.4L236.8 313.6c11.4 8.5 27 8.5 38.4 0L492.8 150.4c12.1-9.1 19.2-23.3 19.2-38.4c0-26.5-21.5-48-48-48H48zM0 176V384c0 35.3 28.7 64 64 64H448c35.3 0 64-28.7 64-64V176L294.4 339.2c-22.8 17.1-54 17.1-76.8 0L0 176z"/>
</svg>
path d の手前に fill
svg の中に width,height, aria-hidden, focusable, data-prefix(fontawasome の時だけ)を入れ込んで OK、参考 ↓
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" width="35" height="26" class="icon" aria-hidden="true" focusable="false" data-prefix="fas" ><path fill="#fff" d="M128 0c17.7 0 32 14.3 32 32V64H288V32c0-

## sass のカラー登録や、svgfill での指定方法

カラーを変数にする
$color-primary: #3498db;
// svgでfillで使用したいときは変数にクラスを再設定する必要あり
.color-primary {
    fill:$color-primary;
}のように指定する
html では-- path の fill にカラー指定をせず、svg に sass コンパイルの color-primary を指定する方法 <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" width="26" height="26" class="icon color-primary" aria-hidden="true" focusable="false" data-prefix="fas"><path d="M406.5 399.6C387.4 352.9 341.5 320 288 320H224c-53.5 0-99.4 32.9-118.5 79.6C69.9 362.2 48 311.7 48 256C48 141.1 141.1 48 256 48s208 93.1 208 208c0 55.7-21.9 106.2-57.5 143.6zm-40.1 32.7C334.4 452.4 296.6 464 256 464s-78.4-11.6-110.5-31.7c7.3-36.7 39.7-64.3 78.5-64.3h64c38.8 0 71.2 27.6 78.5 64.3zM256 512A256 256 0 1 0 256 0a256 256 0 1 0 0 512zm0-272a40 40 0 1 1 0-80 40 40 0 1 1 0 80zm-88-40a88 88 0 1 0 176 0 88 88 0 1 0 -176 0z"></svg>

## 合体処理 1

<svg xmlns="http://www.w3.org/2000/svg" width="43.238" height="26.635" viewBox="0 0 43.238 26.635" class="icon"><g fill="#fff" clip-path="url(#a)"><path d="M13.318 6.417a6.9 6.9 0 0 0-5.173 11.46 4.814 4.814 0 0 1 4.367-2.787h1.612a4.814 4.814 0 0 1 4.367 2.787 6.9 6.9 0 0 0-5.173-11.46m0 7.4a2.569 2.569 0 1 1 2.569-2.569 2.569 2.569 0 0 1-2.569 2.569"/><path d="M39.779-.001H3.459A3.463 3.463 0 0 0 0 3.459v19.716a3.463 3.463 0 0 0 3.459 3.459h36.32a3.463 3.463 0 0 0 3.459-3.459V3.459a3.463 3.463 0 0 0-3.459-3.46M13.317 21.731a8.414 8.414 0 1 1 8.414-8.414 8.423 8.423 0 0 1-8.414 8.414m18.733-1.458h-6.189a.757.757 0 0 1 0-1.513h6.189a.757.757 0 1 1 0 1.513m5.508-4.133h-11.7a.757.757 0 0 1 0-1.513h11.7a.757.757 0 0 1 0 1.513m0-4.133h-11.7a.757.757 0 0 1 0-1.513h11.7a.757.757 0 0 1 0 1.513m0-4.133H32.05a.757.757 0 1 1 0-1.513h5.508a.757.757 0 0 1 0 1.513"/></g></svg>

## 合体処理２

<svg xmlns="http://www.w3.org/2000/svg" width="24.6" height="18.6" viewBox="0 0 24.68 18.65"><g style="fill:#2c73c6; stroke-width:0"><path d="M4.44 0c.59.01 1.83.25 5.33.88 3.85.7 5.01.93 5.18 1.02.36.22.65.54.82.93.15.42.15.87 0 1.28-.06.16-.68 1.32-1.39 2.59S13.1 9.02 13.1 9.03s2.16 1.21 4.79 2.66c.76.42 1.46.81 2.1 1.16a9.24 9.24 0 0 0-2.22-.27c-.85-.05-1.7.06-2.51.33-2.41.72-4.77 2-7.24 2.71-2.49.72-2.45-1.18-2.18-2.03.24-.47.29-.61 2.08-3.77 1.53-2.7 2.73-4.94 2.72-4.94s-1.45-.27-3.2-.59-3.3-.62-3.43-.66c-.52-.17-.95-.54-1.18-1.03-.11-.24-.16-.5-.13-.76-.03-.26.01-.52.13-.76.19-.4.51-.72.9-.92.23-.11.47-.17.71-.16Zm-.76 5.78c1.89 0 3.42 1.53 3.42 3.42s-1.53 3.42-3.42 3.42S.25 11.09.25 9.2s1.53-3.42 3.42-3.42m14.06 7.54c1.75-.03 3.46.49 4.9 1.48.71.54 1.35 1.17 1.89 1.88.3.49.14 1.13-.35 1.42-.19.11-.41.17-.62.15-.66 0-.9-.51-1.12-.74a6.387 6.387 0 0 0-4.75-2.07c-3.18.09-6.46 2.78-10.1 3.19-2.28.25-5.89-.68-7.27-3.03-.91-1.49.34-2.57 1.46-1.43a6.533 6.533 0 0 0 5.37 2.36c2.84-.21 5.4-2.06 8.07-2.86.81-.27 1.66-.38 2.51-.32Z"/></g></svg>

## スクロール可能の可視化

スクロールヒントサイトページ　https://appleple.github.io/scroll-hint/
・header に　<link rel="stylesheet" href="https://unpkg.com/scroll-hint@latest/css/scroll-hint.css">

<script src="https://unpkg.com/scroll-hint@latest/js/scroll-hint.min.js"></script>を入力して
<div class="js-scrollable">
        <table>
            <thead>
                <tr>
                    <th>title1</th>
                    <th>title2</th>
                    <th>title3i</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>Lorem ipsum dolor sit amet consectetur adipisicing elit. Deleniti, eaque recusandae corrupti, ex modi ceat recusandae minus, aut est assumenda.</td>
                    <td>id reprehenderit dolores molestium perferendis enim, minus cumque itaque aliquam.
                    </td>
                    <td>as voluptates dolor officia ipsam. Quisquam accusanti
                    </td>
                </tr>
            </tbody>
        </table>
    </div>で囲んで <script>
        new ScrollHint('.js-scrollable', {
            scrollHintIconAppendClass: 'scroll-hint-icon-white',
            applyToParents: true,
            i18n: {
                scrollable: 'スクロールできます'
            }
    });
    </script>で処理する

## サンプル画像の用意

グレー背景とサイズ
<img src="https://via.placeholder.com/300x200" alt="">
背景色フリーとサイズとテキスト
<img src="https://via.placeholder.com/300x200/0cf/fff/?text=textsample" alt="">

<!-- memo3 -->

電話アプリ起動をスマホのみ設定する
最大 767 の時 →max-width:767?
最小 768 の時 →768 以上で
@media (min-width: 768px) {
a[href^="tel:"] {
pointer-events: none;
}
}

テキストサイズの、最小、推奨、最大
font-size: clamp(16px, 2.5vw, 23px);clamp(16px, 3vw, 30px);
font-size: clamp(35px, 4vw, 51px);
font-size: clamp(22px, 3.8vw, 30px);
clamp(28px, 6.5vw, 50px);
font-size: clamp(12px, 1.5vw, 24px);clamp(12px, 1.5vw, 16px);

ゆっくり表示される
transition: right 0.3s ease-in-out;

背景透過
background-color: rgba(128, 128, 128, 0.5);

影付きボタン、hover 動き
.aside-shadow {
box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
border-radius: 8px 0px 0px 8px;
transition: box-shadow 0.5s ease;
}
.aside-shadow:hover {
box-shadow: 4px 4px 8px rgba(0, 0, 0, 0.7);
transform: translate(3px);
}

背景画像処理
.sectionHero {
background-image: url("../image/bgimg_hero_pc.jpg");
width: 100%;
height: 964px;
background-size: cover;
background-position: right bottom;
overflow: hidden;
}

画像のサイズ 600px かまたは 80%のどちらかで
しい裁縫に設定する
width: min(600px, 80%);

プラン表のコツ
/_=================================
plan
================================= _/
.sectionPlanTitle::after {
content: "";
display: block;
width: 10%;
height: 2px;
background: #00a99d;
position: absolute;
left: calc(50% - (10% / 2));
margin-top: 10px;
}
.attention-plan {
list-style-type: "※";
list-style-position: inside;
text-indent: -16px !important;
padding-left: 20px !important;
line-height: 1.8rem;
}
section[class*="section-py"] {
padding-top: 80px;
padding-bottom: 80px;
}
.section-content {
width: 100%;
padding: 0px 12%;
}
.sectionPlan {
width: 100%;
height: auto;
align-items: center;
}
li[class^="planbox"] {
width: 100%;
height: 100px;
background: white;
padding: 8px 30px;
border-radius: 15px;
border: 4px solid;
box-sizing: border-box;
align-items: center;
}
li[class^="planbox"] h1 {
font-size: 30px;
letter-spacing: 8px;
font-weight: 500;
min-width: 225px;
}
li[class^="planbox"] .color3 {
padding: 0px 30px;
}
li[class^="planbox"] .amount {
font-size: 50px;
font-weight: 700;
align-self: center;
}
li[class^="planbox"] .yen {
font-weight: 700;
text-align: center;
font-size: 23px;
letter-spacing: 0.2rem;
align-self: center;
line-height: 25px;
padding-top: 10px;
}
li[class^="planbox"] .tax {
font-weight: 500;
font-size: 16px;
}
li[class*="color1"] {
color: #59b5d2;
}
li[class*="color2"] {
color: #9cbc3c;
}
p[class*="color3"] {
color: #000000;
}

途中挿入する横幅ワイドの decoration 100vw ライン
.decoline1 {
position: relative;
height: auto;
}
.decoline1::after {
content: "";
width: 100%;
position: absolute;
z-index: 10;
background: url("../image/deco_vcutline3.svg") no-repeat center top / 100%
auto;
aspect-ratio: 1 / 0.1;
bottom: 0;
}

画像を中に入れて同じ高さなどに制御する box

レスポンシブ画像の設定
picture タグ

<!-- 3-a 画像設定sp767以下、pc768以上、他 -->

                        <div class="p-hd__logo-img">
                            <picture>
                                <source media="(min-width:768px)" srcset="./images/common/hd_logo.png.webp 1x,
                                images/common/hd_logo@2x.png.webp 2x">
                                <source media="(max-width:767px)" srcset="./images/common/hd_logo-sp.png.webp 1x,
                                images/common/hd_logo-sp@2x.png.webp 2x">
                                <img src="./images/common/hd_logo.png.webp" width=145 height="42" alt="ロゴ画像：佐渡の海鮮居酒屋 | うめえっちゃ" class="-img">
                            </picture>
                        </div>

media 属性：メディアクエリを使用して、どの条件でその画像を使用するかを指定します。
srcset 属性：条件に合致したときに表示する画像を指定します。複数の解像度の画像を提供する場合は、1x や 2x といったスケールを指定します。
<picture>タグ内の<img>要素は、フォールバック（バックアップ）として機能します。ブラウザが<picture>タグや<source>要素をサポートしていない場合や、指定した条件に一致する画像が見つからない場合に表示されます。
ページのパフォーマンスを向上

セクションごと余白が違う時
１：Padding だけのクラスを設定する
２：marign と横幅を指定したクラスを設定する
で、セクションごとに 2 と 1 のサイズを決めて組み合わせて 1 つのセクションと余白をセットでニコイチで完成させるとレイアウト組がしやすい

<section class="l-section" id="message">
                <!-- 7　レスポンシブ対応できるc-width -->
                <div class="p-section c-width">
                    <h2 class="c-section-title">日本海の恵み<br> 佐渡の海鮮料理でおもてなし</h2>
                    <div class="p-message-text">
                        <p class="c-section-text">
                            テキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキスト
                        </p>
                    </div>
                </div>
            </section>
            <section class="l-section" id="message">
                <!-- 7　レスポンシブ対応できるc-width -->
                <div class="p-section c-width2">
                    <h2 class="c-section-title">日本海の恵み<br> 佐渡の海鮮料理でおもてなし</h2>
                    <div class="p-message-text">
                        <p class="c-section-text">
                          テキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキスト
                        </p>
                    </div>
                </div>
            </section>
scss設計
.c-width {
  max-width: 940px;
  margin: 0 auto;
}
.c-width2 {
  max-width: 600px;
  margin: 0 auto;
}

行間 line-height
XD の行サイズ 60 でテキストサイズが 40px であれば
60÷40 で 1.5 なので、line-height1.5 となる

文字間 letter-spacing
XD の文字間 AV が 4px でテキストサイズが 40px であれば
4÷40 で 0.1 なので、letter-spacing0.1em となる

<!-- BEM -->

https://zenn.dev/nagan/articles/dac6fa662f4dab

## 画像やカラーの設定ができたら、余白（各セクション width）を Figma に落とし込み

そこまでは template を使用する

// .l-main {
// padding: 0 0 220px;
// @media only screen and (max-width: 767px) {
// padding: 0 0 96px;
// }
// }

## ２行目インデント、改行、

text-indent: -16px !important;
padding-left: 20px !important;
.p-item-faq {  
 &--question {
font-size: 25px;
line-height: 1.69em;
color: $siteGreen;
font-weight: bold;
text-indent: -40px !important;
padding-left: 40px !important;
&-text {
background: linear-gradient(to bottom, rgb(255, 255, 217, 0) 65%, rgb(255, 255, 217, 0.57) 35%);
}
&-text::before {
content: "Q";
font-size: 35px;
padding-right: 13px;
top: -5px;
position: relative;
}

## 文字と画像のレスポンシブをばっと決めて

clamp と max-width で調整する
pc--none で pc の時に none する（pc の CSS に記述するので sp-only とはしない）
文字はデバイス 400px でためして文字を小さくする前に letter-swpacing も考慮する

## 0628Git 　 pull がうまくいかず？

push を元に戻す作業をした
6/28 の作業を削除し、6/27 の時点に戻した

## ハンバーガーメニュー,cta

\_spnav.scss ファイル
js
//////////////////////////////////////
// pc と sp メニュー切り替え
//////////////////////////////////////
// sp-open
document.getElementById('spnav-open').addEventListener('click', function() {
document.querySelector('.l-spnav').style.display = 'block';
});
document.getElementById('spnav-open').addEventListener('click', function() {
document.querySelector('.l-spnav').style.display = 'block';
});
// sp-close
document.getElementById('spnav-close').addEventListener('click', function() {
document.querySelector('.l-spnav').style.display = 'none';
});

//////////////////////////////////////
// 遷移時にオフセットと非表示
//////////////////////////////////////
// pc
document.querySelectorAll('.p-nav-listbox\_\_title').forEach(function(item) {
item.addEventListener('click', function(event) {
event.preventDefault(); // デフォルトのアンカー動作を防ぐ
const targetId = this.querySelector('a').getAttribute('href').substring(1);
const targetElement = document.getElementById(targetId);

        if (targetElement) {
            const offsetTop = targetElement.getBoundingClientRect().top + window.scrollY - 117; // 117pxオフセット
            window.scrollTo({
                top: offsetTop,
                behavior: 'smooth'
            });
        }
        document.querySelector('.l-spnav').style.display = 'none';
    });

});

// sp
document.querySelectorAll('.p-spnav-listbox\_\_title').forEach(function(item) {
item.addEventListener('click', function(event) {
event.preventDefault(); // デフォルトのアンカー動作を防ぐ
const targetId = this.querySelector('a').getAttribute('href').substring(1);
const targetElement = document.getElementById(targetId);

        if (targetElement) {
            const offsetTop = targetElement.getBoundingClientRect().top + window.scrollY - 70; // 70pxオフセット
            window.scrollTo({
                top: offsetTop,
                behavior: 'smooth'
            });
        }
        document.querySelector('.l-spnav').style.display = 'none';
    });

});

//////////////////////////////////////
// cta ボタン設定
//////////////////////////////////////
// スクロール位置を監視して条件を満たしたら .l-cta-aside を表示する
window.addEventListener('scroll', function() {
const ctaAside = document.getElementById('l-cta-aside');
if (window.scrollY >= 600 && window.innerWidth >= 768) {
ctaAside.style.display = 'block';
} else {
ctaAside.style.display = 'none';
}
});

// PC の場合
@media only screen and (min-width: 768px) {
// 非表示にする
.pc--none {
display: none;
}
}
// sp の場合
@media only screen and (max-width: 767px) {
// 非表示にする
.sp--none {
display: none;
}
}

## responsive @media

①_mediaQuery.scss 作成し＠media を設定しておき読み込みファイル ② は@use "ルート/\_mediaQuery" as \*;
①
// mediaQuery
@charset "utf-8";

/_ responsive setting
======================================================= _/
$breakpoints: (
400: 400px,
768: 768px,
880: 880px,
930: 930px
);

@mixin min($breakpoint) {
    @media (width >= #{map-get($breakpoints, $breakpoint)}) {
        @content;
    }
}
@mixin max($breakpoint) {
@media (width <= #{map-get($breakpoints, $breakpoint)}) {
@content;
}
}
/_ sample
880 以下で
@include max(880) {
flex-direction: column;
align-items: flex-start;
}
_/
②.p-info-numberbox {
flex-direction: nowrap;
align-items: flex-end;
@include max(880) {
flex-direction: column;
align-items: center;
}
}で OK

##　表示タイミング
//////////////////////////////////////
// 表示タイミング
//////////////////////////////////////

$(function() {
$(window).scroll(function() {
// スクロール量を取得
const scroll = $(window).scrollTop();
// 画面の高さを取得
const windowHeight = $(window).height();
// 各.box に対して処理を行う
$(".box, .text, .text80").each(function() {
// それぞれの.box の上端の座標を取得
const boxTop = $(this).offset().top;
// 条件を満たす場合は is-active クラスを付与し、そうでない場合は削除する
if (scroll + windowHeight > boxTop + 300) {
$(this).addClass("is-active");
} else {
// $(this).removeClass("is-active");
}
});
});
});
.text80 {
overflow: hidden;
opacity: 0;
visibility: hidden;
transition: all 2s;
transform: translateY(100px);
}
.is-active {
opacity: 1;
visibility: visible;
transform: translateY(0);
}

## WordPress 管理画面テーマイメージ画像

screenshot.png として 880x600 の画像をルートディレクトリに作成する

## 導入実績カスタムフィールド html から php 変換 → ショートコード、WP 関数変換

        <section class="l-work c-x-center" id="work">
            <div class="l-work-contents c-padding--x50px c-padding--y100px c-margin--0auto">
                <h3 class="l-contents__title">導入実績</h3>
                <hr class="c-title__hr c-title__hr--green c-margin--b100px">
                <ul class="l-work-contents-itemsbox text80">
                    <li class="p-item">
                        <img src="./images/home/pc/img_worklogo.png" alt="">
                    </li>
                    <li class="p-item">
                        <img src="./images/home/pc/img_worklogo.png" alt="">
                    </li>
                    <li class="p-item">
                        <img src="./images/home/pc/img_worklogo.png" alt="">
                    </li>
                </ul>
                <p class="l-work-contents__text c-text--16-0-25">※企業ロゴの掲載は順不同です</p>
            </div>
        </section>
        から、phpに変換後、ショートコードへ

<?php
$args = Array(
    			 'post_type' => 'record_banner',
     			'posts_per_page' => -1,
  				);
   				$the_query = new WP_Query($args);
if($the_query -> have_posts()):
?>
<section class="l-work c-x-center" id="work">
<div class="l-work-contents c-padding--x50px c-padding--y100px c-margin--0auto">
<h3 class="l-contents__title">導入実績</h3>
<hr class="c-title__hr c-title__hr--green c-margin--b100px">
<ul class="l-work-contents-itemsbox text80">
<?php while ( $the_query->have_posts() ) : $the_query->the_post(); ?>
<?php if ( get_field( 'record_img' ) ): ?>
<li class="p-item">
<?php if ( get_field( 'record_link' ) ): ?>
<a href="<?php echo get_field( 'record_link' ) ;?>" target="_blank">
<?php endif; ?>
<img src="<?php echo get_field( 'record_img' ) ;?>" alt="<?php the_title(); ?>">
<?php if ( get_field( 'record_link' ) ): ?>
</a>
<?php endif; ?>
</li>
<?php endif; ?>
<?php endwhile; ?>
</ul>
<p class="l-work-contents__text c-text--16-0-25">※企業ロゴの掲載は順不同です</p>
</div>
</section>
<?php  endif; wp_reset_postdata(); ?>

## WordPRess 変換には

・メディア*プラグインで登録(mediasync でファイル登録可能、または FTP でも OK)
　　ー登録、ーリンクコード変換
・遷移先パス*パスの変換（WP の URL が発行されるのでそれに書き換え）
・ディレクトリ構造
・SCSS の読み込み
・WP カスタムテーマに必須なファイル（index.php、style.css、front-page.php など）

## ページごとに違う header や footer を読み込ませるためには

◾️hedaer-lp.php を読み込ませるページの

<?php get_header(); ?>の部分を、<?php get_header('lp'); ?>にすると読み込むことができる

◾️ テンプレートファイルを固定ページとして使用したいときは
例：固定ページ名（LP サイト）としたいとき、php のファイル名は page-service*lp.php として
リンクさせる必要がある
① 固定ページ名（LPsite）
②page-service_lp.php を作成する
③page-service_lp.php の冒頭にコメントアウトで、<?php
/*
Template Name: LPsite Page
\_/
get_header('lp');
?>と実装
④FTP で themes に header-lp.php と page-service_lp.php を入れてから
⑤ 管理画面の固定ページ編集でテンプレートを選択すると、LPsite が選択できる=このページでは page-service_lp.php ファイルを使用するということになりリンク設定が完了する、header-lp.php も読み込まれている

## header の高さ分、スクロールさせる方法

script.js
$(document).ready(function() {
function updateHeaderHeight() {
var headerHeight = $(".l-header-inner").outerHeight();
$(".l-section").css("padding-top", headerHeight + "px");
}

    function scrollToHash() {
        var hash = window.location.hash;
        if (hash) {
            setTimeout(function() { // ページが完全にロードされた後に少し遅れて実行
                var targetOffset = $(hash).offset().top;
                var headerHeight = $(".l-header-inner").outerHeight();
                $('html, body').animate({
                    scrollTop: targetOffset - headerHeight
                }, 500);
            }, 3000);
        }
    }

    updateHeaderHeight();
    scrollToHash(); // ハッシュに基づいてスクロール

    $(window).resize(updateHeaderHeight);

    $('.l-header-inner a[href^="#"]').on('click', function(event) {
        event.preventDefault();
        var targetId = $(this).attr("href");
        var targetOffset = $(targetId).offset().top;
        var headerHeight = $(".l-header-inner").outerHeight();
        $('html, body').animate({
            scrollTop: targetOffset - headerHeight
        }, 500);
    });

});

## button btn　のサイズ
border-radius: 60px;
が一番綺麗