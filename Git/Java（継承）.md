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

[新車クラス]

継承を利用しない場合・・・・
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

