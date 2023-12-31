# 継承
継承とは、クラスが持っているメンバ（メソッド）を別のクラスに引き継がせること。

継承元のクラスをスーパークラス（親クラス）、引き継いだクラスをサブクラス（子クラス）という

オブジェクト指向の３大要素の一つ。他は、カプセル化とポリモーフィズム。

---
サブクラスの作成　「extends」（読み：エクステンズ）を使用する！

「extends」の前にサブクラス名（子クラス名）、後にスーパークラス名（親クラス名）を指定。
```Java
pubulic class NewCar extends BaseCar{
```
---

#　継承のメリット

継承を利用しない場合・・・・

[新車クラス]
```java
public class NewCar {
    /**
     * 製造元
     */
    private static final String MANUFACTURER = "○○自動車";
    
    /**
     * 製造元と販売価格を出力する
     * @param price 販売価格
     */
    private void print(int price) {
        System.out.println("製造元は" + MANUFACTURER);
        System.out.println("販売価格は" + price + "円");
    }
    
    /**
     * 新車の製造元と販売価格を出力する
     * @param price 販売価格
     */
    public void printNewCar(int price) {
        System.out.println("新車です");
        print(price);
    }

```
[中古クラス]
```java
public class OldCar {
    /**
     * 製造元
     */
    private static final String MANUFACTURER = "○○自動車";
    
    /**
     * 製造元と販売価格を出力する
     * @param price 販売価格
     */
    private void print(int price) {
        System.out.println("製造元は" + MANUFACTURER);
        System.out.println("販売価格は" + price + "円");
    }
    
    /**
     * 中古車の製造元と販売価格を出力する
     * @param price 販売価格
     */
    public void printOldCar(int price) {
        System.out.println("中古車です");
        print(price);
    }
}
```
上記のだと同じ記述があり可読性や保守性が良くない。

よって・・共通的な部品は「共通クラス」として管理するか「継承」して管理する！

---
継承を利用してみる。

[車の基本クラス]
```java
public class BaseCar {
    /**
     * 製造元
     */
    private static final String MANUFACTURER = "○○自動車";
    
    /**
     * 製造元と販売価格を出力する
     * @param price 販売価格
     */
    protected void print(int price) {
        System.out.println("製造元は" + MANUFACTURER);
        System.out.println("販売価格は" + price + "円");
    }
}
```
[新車クラス]
```java
public class NewCar extends BaseCar {
    
    /**
     * 新車の製造元と販売価格を出力する
     * @param price 販売価格
     */
    public void printNewCar(int price) {
        System.out.println("新車です");
        print(price);
    }
}
```

[中古クラス]
```java
public class OldCar extends BaseCar {
    
    /**
     * 中古車の製造元と販売価格を出力する
     * @param price 販売価格
     */
    public void printOldCar(int price) {
        System.out.println("中古車です");
        print(price);
    }
}
```
上記では、「新車クラス」と「中古クラス」は「車の基本クラス」を継承している。

継承を使うことで、車の共通的な機能はスーパークラス（親クラス）で管理し、サブクラス（子クラス）では、サブクラス独自の機能を実装するだけとなる。

継承を利用することで、何度も同じソースコードを書かずに済み、読みやすいソースコードを書くことが可能になる！！！

---
# オーバーライド

オーバーライドとは、スーパークラスで定義されているメソッドを、サブクラス内で再定義すること

スーパークラスのメソッドをサブクラス用に、上に重ねて定義すること。(上書きではない)

オーバーライドを定義するには、いくつかの規定がある

・戻り値の型、メソッド名、引数型、引数の数、引数の並びも同じにする必要がある   
・スーパークラス以上の広い範囲のアクセス修飾子にする必要がある(大体public)

---

```ExClass.java
class ExClass {
    public void increase(int i) {  //引数を10倍にするメソッド
        int x = i * 10;
        System.out.println(x);
    }
}
```
```SubExClass.java
class SubExClass extends ExClass {
    public void increase(int i) {  //引数を1000倍にするメソッド
        int x = i * 1000;
        System.out.println(x);
    }
}
```

```ExSubClassMain.java
public class ExSubClassMain {
  public static void main(String[] args){
    //サブクラスのインスタンス化
    SubExClass sub = new SubExClass();
    sub.increase(5);
  }
}
```

結果
```
5000
```
「increase」メソッドでも、スーパークラスでは引数を10倍にするメソッド、サブクラスでは1000倍にするメソッドにオーバーライドしてる。
結果、サブクラスでオーバーライドされた引数(5)を1000倍(5000)にするメソッドが実行。

---



