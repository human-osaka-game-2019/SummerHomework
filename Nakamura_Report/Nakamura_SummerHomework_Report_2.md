# リーダブルコード２
## 第三章
> **誤解されない名前**

本章では、「誤解される名前」に気をつけろという点に触れようと思う。
#### 名前が「他の意味と間違われることがないだろうか？」と何度も自問自答する

ここでは、積極的に「誤解」を探してほしい。
そうすれば変更が必要なあいまいな名前が見つかるだろう。

例：filter   
filterという言葉は曖昧であり、「選択する」と考える人、「除外する」と考える人がいるだろう。
そのような誤解を解くために、「選択する」関数の場合は「select」、「除外する」関数の場合は「exclude」にするべきだろう。

> **限界値を含めるときはminとmaxを使う**

ショッピングカートには商品が10点までしか入らないとしよう。
```
CART_TOO_BIG_LIMIT=10;

if shopp_cart.num_items()>=CART_TOOBIG_LIMIT;
```
このコードではカートにある商品が多すぎる！とエラーが出る。
これを修正するには「　>=を> 」に変えればよい
あるいは「CART_TOO_BIG_LIMIT=10をCART_TOO_BIG_LIMIT=11」に変えればよい。
だけど、根本的な問題は「CART_TOO_BIG_LIMIT」という名前が曖昧なことだ。
#### 限界値を明確にするには、名前のまえにmax_やmin_を付けよう
この場合は、「MAX_ITEM_IN_CART」という名前にすべきだ。

> **包含/排他的範囲にはbeginとendを使う**

プログラミングの命名規約では包含/排他的範囲にはbeginとendを使うことが多い。
しかし、endは曖昧だ。
例えば、本の終盤を読んでいるのendは包含的だ。
残念ながら英語には「ちょうど最終の値を超えたところ」を意味する単語がない。
なので、これが最善の選択といえるだろう。

> **ブール値の名前**

ブール値の名前にはtrueとfalseを明確にしなければならない。
危険な例
```
bool read_password=true;

```
これには二つの解釈の仕方がある。
1. これからパスワードを読み取る必要がある
2. パスワードをすでに読み取っている

ここでは「read」の代わりに「need_password」、「user_is_authenticated」を使ったほうがいい。
#### 複数の名前を検討する
名前を決めるときは、複数の候補を検討し、それぞれの長所について話し合うのが普通だ。

最善の名前とは、誤解されない名前である。
つまり君のコードを読んでいる人が君の意図を正しく理解できるということだ。
英語の単語は、プログラムで使うことにおいて意味が曖昧なことが多い。
名前を決める前に誤解のない名前か想像してみよう。

## 第四章
> **美しさ**

優れたソースコードとは、「目に優しい」ものでなければならない。
本章では、こーどを読みやすくするための余白、配置、順序について説明する。
具体的には僕たちが使っている3つの原則についてだ。
1. 読み手が慣れているパターンと一貫性のあるレイアウトを使う
2. 似ているコードは似ているように見せる
3. 関連するコードをまとめてブロックにする

> **なぜ美しさが大切なのか**

```
class:class StatsKeeper{
public:  
list<double>
past_items
;
```
と
```
class:class StatsKeeper{
public:  
    
    list<double> past_items;
```

見た目が美しいコードのほうが使いやすいのは明らかだ。
考えてみれば、プログラミングの時間のほとんどはコードを読む時間である。
さっと流し読みできれば誰にとっても使いや数コードであるといえるだろう。

> **一貫性のある簡潔な改行位置**

コードの見た目を一貫性のあるものにするには、適切な改行を入れよう。
```
public static final TcpConnectionSimulator wifi=new TcpConnectionSimulator(
      ・・・・・・）;
public static final TcpConnectionSimulator t3_fiber=
 new TcpConnectionSimulator(
      ・・・・・・）;

```
うえの例は悪い例である。

> **縦の線をまっすぐにする**

縦の線をまっすぐにすれば文章に目が通しやすくなる。
列を「整列」させれば、コードが読みやすくなる場合がある。

```
detailes =request.POST.get('details')
location =equest.POST.get('location')
phone    =request.POST.get('phone')

```
このようにコードを整列しておけば、二つ目のequestがタイプミスと気づくことができる。
これは、「似ているコードは似ているように見せる」いい例でもある。

> **コードを段落に分ける**

```
public static final TcpConnectionSimulator wifi=
new TcpConnectionSimulator(・・・・・・）;
public static final TcpConnectionSimulator t3_fiber=
new TcpConnectionSimulator(・・・・・・）;

```
こんな塊のコードは誰も読む気がしない。
しかし、だんらくにわけるとどうだろう。
```
public static final TcpConnectionSimulator wifi=new 
    TcpConnectionSimulator(
      ・・・・・・）;
public static final TcpConnectionSimulator t3_fiber=
    new TcpConnectionSimulator(
      ・・・・・・）;

```
これでコードにざっと目を通せるようになった。
長い段落が好きなプログラマーもいれば、短い段落が好きなプログラマーもいるためコードを分割する方法はいとそれぞれである。

> **個人的好みと一貫性**

最終的には個人の好みになってしまうこともある。たとえばクラスの位置がそうだ。
```
class Logger{

・・・
}；

```
または、
```
class Logger
{

・・・
}；

```

どちらを選んだとしてもコードの読みやすさに大きな影響はない。
でも、このスタイルを混ぜてしまうとすごく読みにくいものになる。
なので、プロジェクトの規約にしたほうがよいだろう。
一貫性のほうが大事なことだからだ。

> **ここまでで感じたこと**

第四章のでのことは、本当に共感できる箇所があった。
チーム制作であまり流し読みしかできなかったが、興味がわいてきたので、また読み直そうと思う。

