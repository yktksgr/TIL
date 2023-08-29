# Javaにおける配列

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

Javaで配列を使用する際は、以下の手順が必要。

① 配列の宣言を行う   
```Java
int[] scores;
```
int型の整数を格納する配列の宣言はint[] scores;と記述。   
この「int」は要素として格納したいデータ型を指定するもので、例えばlong型の整数を格納する配列ならlong[] scores;のように宣言する

② 配列の要素を作成し、配列に代入する   

```Java
scores = new int[3];
```
int型の要素を３つ作成し,配列scoresに代入。

③ 配列の要素に値を代入する   
```Java
scores[0] = 1;
```
配列scoresの1番目の要素に「1」を代入している。

---

# 配列のさまざまな記述方法

① 配列の宣言と同時に、要素の作成も行う方法
```Java
int[] scores;
scores = new int[3];
```
上記は下記のように１行で記述可能！！

```Java
int[] scores = new int[3];
```





