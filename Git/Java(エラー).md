# Javaの設計

# エラーの種類
Javaプログラムの場合は大きく3つに分類。

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
---

例外時における３つのエラークラス
# Errorクラス（エラークラス）
エラークラスは、プログラムが実行中に致命的な問題が発生した場合にスロー（発生）されるクラス。   
これらのエラーは、通常、プログラムが正しく動作できないほど深刻な問題を示します。次のようなエラーが含まれる。

OutOfMemoryError（メモリ不足エラー）:   
プログラムが使いすぎのメモリを要求すると、これがスローされます。例えば、大きすぎるデータを扱うときに発生。

StackOverflowError（スタックオーバーフローエラー）:   
プログラムの関数呼び出しが無限ループに陥ると、スタックがいっぱいになり、このエラーが発生。

これらのエラーは通常、プログラマが修正する必要がある非常に深刻な問題を示す。

# Exceptionクラス（例外クラス）
例外クラスは、プログラムが実行中に問題が発生した場合にスローされるクラスだが、エラークラスと比較して一般的な問題を示す。例外はプログラムの実行を中断しないで処理できる可能性。次のような例外が含まれる。

ArithmeticException（算術例外）:   
0で割り算をしようとすると、この例外が発生。

NullPointerException（ヌルポインタ例外）:   
変数が何も指していない（null）状態で、それを使用しようとするとこの例外が発生。

これらの例外は、プログラムの正しい動作を妨げる可能性があるが、適切なエラーハンドリング（例外を処理する方法）を行うことで、プログラムがクラッシュせずに続行できるようになる。

# RuntimeExceptionクラス（ランタイム例外クラス）　　　
ランタイム例外クラスは、例外クラスの一種で、特にコンパイラがチェックしない（チェック例外ではない）例外を示す。つまり、プログラムがコンパイル時にチェックしないため、実行時に発生する可能性がある例外。次のような例外が含まれる。

ArrayIndexOutOfBoundsException（配列の添え字範囲外例外）:      
配列の要素にアクセスしようとしたとき、存在しない添え字を指定した場合に発生。

NumberFormatException（数値フォーマット例外）:      
文字列を数値に変換しようとしたとき、正しくないフォーマットの文字列が与えられた場合に発生。

ランタイム例外は、プログラムの実行時に発生する可能性があるが、プログラマが明示的に例外処理を行わなくても、発生した場合はプログラムがクラッシュする。したがって、プログラマはランタイム例外に注意を払う必要がある。

要するに、エラークラスは非常に深刻な問題を示し、例外クラスは一般的な問題を示し、RuntimeExceptionクラスは実行時に発生するかもしれない問題を示すもの。プログラマはこれらのクラスを理解し、適切に処理する方法を学ぶことが重要！！！

---

# スロー宣言

・メソッドがどの種類の例外をスローするかを明示的に宣言するもので、プログラマーにとってそのメソッドの使用方法や例外処理がどのように行われるべきかを理解しやすくするもの

以下例　「割り算」の関数、ゼロで割るとエラーが発生するもの
```java
public int divide(int numerator, int denominator) throws ArithmeticException {
    if (denominator == 0) {
        throw new ArithmeticException("ゼロで割ることはできません");
    }
    return numerator / denominator;
}
```
throws ArithmeticException という部分がスロー宣言。

この関数を使うプログラマーに「ゼロで割る可能性があること」を伝えている！



