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
