# リーダブルコード  
- ## 優れたコードとは、プログラマーという人たちはのは、何となく直感でプログラミングのことを決めていることが多い。  

- ## 鍵となる考え  
  - コードは自分以外の人たちがみてすぐに理解できるように書かなければならない。  

- ## 表面上の改善  
  - 読みやすさの始まりは「表面上」の改善。  
  適切に名前を選び、わかりやすいコメントをのこし、コードをきれいにフォーマットします。  
  こうした変更は簡単にできます。プログラムの変更やリファクタリングしなくても  
  入れ替え可能だ。  

- ## 明確な単語を選ぶ  
  - プログラムに使われている名前ははっきりしないものが多い。たとえば、tmpなど  
  sizeやgetみたいに一見すると問題がなさそうな名前であっても、  
  情報が含まれていないことがある。  

- ## 「名前に情報を詰め込む」  
  - 「名前に情報を詰め込む」には、明確な単語を選ばなければならない。  
  「空虚な」単語は避けるべき。  

- ## tmpやretvalなどの汎用的な名前をさけよう  
  - tmp・retval・fooのような名前をつけるのは、「名前のことなんて考えていません」  
  と言っているようなものです。  
  このような「空虚な名前」をつけるのではなく、エンティティの値や目的を表した名前を選ぼう。  
    
- ## ループイテレータ  
  - i , j , k , iterなどの名前は、インデックスやループイテレータでよく使われている。  
  汎用的な名前だけど、　これだけで「ぼくはイテレータ」　という意味になるので問題ない。


