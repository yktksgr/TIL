# Javaの設計

# エラーの種類
Javaプログラムの場合は大きく3つに分類できます。

文法エラー(syntax error)    
実行時エラー(runtime error)   
論理エラー(logic error)   

実行時のエラー 一覧

エラーメッセージ|意味|
--- | --- |
java.lang.NoClassDefFoundError |	必要なクラスが存在しない
java.lang.NoSuchMethodError |	必要なメソッドが存在しない
java.lang.NullPointerException |	参照したオブジェクトの値がnullである
java.lang.ArrayIndexOutOfBoundsException | 範囲外の配列のインデックスにアクセスしている
java.lang.NumberFormatException | 文字列を数値型にキャストできない
java.lang.UnsupportedClassVersionError | コンパイル時と、実行時のJavaのバージョンが異なる
java.lang.StackOverflowError| メモリのスタック領域が不足している

上記の共通点はチーム開発でコード記述時点では予防しにくい。そのためにエラーについて対応する文法と仕組みがある

# try-catch文
プログラムの中で例外が発生する可能性がある処理に利用。   
try-catch文を使うことで、例外が発生する場合、しない場合のそれぞれの処理を分けることができる。　　　
また、finallyを使って例外の有無に関わらず、最後に必ず実行される処理を記述可能。

```java
try{
  例外が発生する可能性がある場合の処理
}catch() {
  例外が発生した場合の処理
} finally {
  例外の有無に関わらず、最後に実行される処理
}

```


