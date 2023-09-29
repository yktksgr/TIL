# 拡張for文
```Java
for ( 要素を格納する変数宣言  :  配列あるいはArrayListの変数名) {
  取り出した要素を使用して行う処理
}
```

① 配列、あるいはArrayListから要素を1つ取り出す   
② 取り出した要素を変数に代入する   
③ {}内の処理を行う   
④ 配列、あるいはArrayListの要素数分だけ処理を繰り返す   


```Java
for(int score : scores) {
  System.out.println(score);  
}
```
変数scoresから要素を取り出し、ing型の変数scoreに代入するという動作   
Rubyのeachメソッドとは書き方が異なるが、使い方は似ている！

