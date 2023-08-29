# Javaにおける配列、Rubyの違い

Javaの配列は、格納する要素の数を最初に決める必要があり、かつ後で要素数を変更できない   
要素を増やす場合は、ArrayListというリストの一種を使用する

---

```Java
int[] numbers = new int[5]; // 5つの整数を格納できる配列を作成
numbers[0] = 1;
numbers[1] = 2;
numbers[2] = 3;
numbers[3] = 4;
numbers[4] = 5;
```

要素数が5で初期値が設定された整数の配列ができる。

---



