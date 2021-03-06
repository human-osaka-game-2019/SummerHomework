# Readablecode Report

目次
- 『[訳者まえがき](##役者の前書き)』
- 『[はじめに](##はじめに)』
- 『[１章](##１章)』
- 『[２章](##２章)』

## 役者の前書き
。
## はじめに

## １章

#### 優れたコードとは？
でも
以下のコードはコード的には優れているし、簡潔にまとめられている。
```
	for (int a = 0; a < 10; a++)
		printf("%d",a);
```

そして、以下のコードはコード的には優れてはいないが、見て安心できる。
```
	for (int a = 0; a < 10; a++)
	{	
        printf("%d",a);
        }
```

当然、前者のコードの方が簡潔にまとめられていて、使う行数が少ない。
しかし、後者の方はコード自体はまとめられてはいないが、他の人から見た時にはとても見やすくないだろうか。  
このことから、どちらのコードが「優れている」とは言いにくいのではないだろうか。

#### 読みやすさの基本理念

これは、よく自分がしてしまうことなのだが。  
自分の書いたコードを見せた時に「なにこれ、考え方は面白いけど何かいてるのかよくわからん」とよく言われてしまう。   
これは、誰もが慣れてきたら起こりうる自分の考えたコードが一番わかりやすい、基、自分しかわからないコードを多く書いてしまう状態のコードをみせた時の反応です。  
ここで言う、読みやすさとは他の人から見た時の見やすさ。  

#### 小さなことは絶対にいいこと

コードをまとめるのたり、短縮するのはコードを書く上でとても大切なことだがそれでコードを読み解く時間が多くかかってしまっては、元も子もない。  
なので、コードを短くするならば、コメントを残す等して「理解するまでにかかる時間」を短くすることが大切になるようだ。  

#### 「理解するまでにかかる時間」は競合する？

以上の文を見てきて、ふと「コードの効率化、設計をうまくする、テストしやすいとかはどうするんだ？」と思ったりはしないだろうか。  
しかし、実際にやってみると、他の人に見やすいコードを書いた場合はコードレビューが早かったりなど、結構メリットがあったりする。  

#### でもやるんだよ

やってみると、分かるが実際やってみると、とてもめんどくさい...  
だが、これが出来ればもっと優秀な Pg になれると思うので頑張りたい。  


## ２章

#### 明確な単語を選ぶ

これは基本的に、変数名、関数名でよく言われることだが  
例えば、乱数を入れる変数、関数名は。
```
int a;
```
より  
```
int random;
```
の方が見てわかりやすいのではないか？

つまる所、その変数、関数が何を示すのかを明確にするような単語を使おう!!!  
ということだ。  

#### tmp や retval などの凡用的な名前を避ける

これはよくある、使いやすい名前を多く使ってしまう事で、「名前空間の汚染」とかが起こってしまうので、避けよう!!!ということです。  
例えば、 tmp はよく入れ替え関数に使用される。  
しかし、よく tmp は一時的な値の保管に使われる為、使用頻度がとても高くなる。  
だから、他の所で使われた時に何の為の　tmp なのかがわからなくなる為に使用を避けた方あ良いということです。

#### 抽象的な名前よりも具体的な名前を使う

これについてはコードを書くときに
「計算する関数」
```
calculate();
```

 より「足し算をする関数」と読むことが出来る
```
addition();
```
にした方が、関数名を見ただけでどんなことをしている関数なのかが一目でわかるため抽象的な名前よりも具体的な名前を使用しようということ。

#### 名前を情報を追加

これは関数の引数などを書くときにその引数が持って来る情報を追加するといいう物。  
```
Rotate(float degrees_cw)
```
などのことです。  

特に同じ名前で別 cpp などで使うときに競合しないようにするために、情報を＋１を追加するといい、ぐらいな感じである。  

#### 名前の長さを決める

この問題は人によって、チームによって考え方、規則によって違うので一概に良いとは言えないが。  
局単に小さい関数内であれば、一文字変数、一文字スコープをしても良いという意見と、ながくてもいいのでわかりやすければいい、といった風なことです。

#### 名前のフォーマットで情報を伝える

これはよく使用されることなのだが、クラス、構造体を同時に使用した場合両方とも、 strct.Hp class.Hp  の様に記入する為、前文では strct class と書いてあるため、分かりやすいがもし少し違うだけなので、区別しやすいように m_ の様に変数等につけよう、という話


