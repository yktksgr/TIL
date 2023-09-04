# ArrayListとは
「可変長配列」を使用するための仕組み。   
可変長配列とは、文字通り長さ（要素数）を変更できる配列のこと

噛み砕くと・・・   
ArrayListはデータを入れるためのリストで、そのリストの中にデータを入れたり、取り出したり、削除したりすることができる。
そして、ArrayListは柔軟で、必要に応じてデータを変更できるのが特徴。

---
# ArrayListの使い方

① ライブラリをインポートする   

② ArrayListの宣言を行う 
```Java
ArrayList<~> 変数名 = new ArrayList<~>();
```
ジェネリクスとは、「総称型」とも呼ばれコレクションフレームワークのような汎用的なクラスやメソッドを特定の型に紐付ける仕組みのこと。   
例えば、ジェネリクスにString型を設定すると、生成された入れ物にはString型の値しか登録できないようになる。

③ ArrayListに値を代入する   

④ ArrayListから要素を取り出す   

---

# ArrayListを順に取り出す
ArrayListに格納された値を一つずつ取り出す方法は３パターン

1. for文を利用してArrayListを取り出す
```java
for (初期化式; 条件式; 変化式) {
    // 繰り返す処理
}
```
2.拡張for文を利用してArrayListを取りだす
```java
for ( 配列の型名 変数名 : 配列名) {
    // 処理
}
```
拡張for文を利用することですっきりと簡潔にまとめることができる!   
ただし、拡張for文は先頭要素から1つずつ値を取り出す必要がある点がある。

3.Iterator（イテレータ）を利用してArrayListを取り出す

Iteratorとは、コレクションの要素を順に処理する場合に使用するもの。矢印「→」のようなイメージ
```java
Iterator<リスト要素の型> sample = リスト変数.iterator(); #宣言方法

while(sample.hasNext()) {
    リスト要素の型 e = sample.next();
    // 要素を用いた処理
}
```
---
# LinkedList
LinkedListはListと継承関係にあり、同様にListと継承関係にあるArrayListの兄弟のようなクラス

ArrayListパターン
```java
import java.util.ArrayList;

public class Template {

    public static void main(String[] args) {

        ArrayList<String> fruits = new ArrayList<>();

        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");

        System.out.println("取り出されたフルーツは" + fruits.get(1) + "です");
    }

}
```

LinkedListパターン
```java
import java.util.LinkedList;

public class Template {

    public static void main(String[] args) {

        LinkedList<String> fruits = new LinkedList<>();

        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");

        System.out.println("取り出されたフルーツは" + fruits.get(1) + "です");
    }

}
```

