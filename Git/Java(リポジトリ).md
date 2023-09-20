# リポジトリ
Javaアプリでデータベースを利用する際は、「リポジトリ」を作成する

リポジトリとは、SQLの操作をJavaのメソッドとして定義するためのもの。   
※Gitで使用するリポジトリとは別のもの！！！

Railsの場合、Javaのリポジトリに相当するものはあらかじめ用意されている。   
例えば、RailsでTweet.allのようにallメソッドを実行することで、Tweetsテーブルのデータ全件を取得可能。

これは、allメソッドを実行すると「select * from tweets」というSQLが発行されることがあらかじめ定義されている。   
このような定義はJavaの場合自分で実装する必要がある、その際使用するのがリポジトリとなる！

---
MyBatisでSelect文を使ったメソッドを定義する場合は、以下のように記述
```java
@Select("発行したいSQL")
返り値のデータ型 メソッド名;
```

postsテーブルから全件データを取得するための「findAll」というメソッドを定義
```Java
@Select("select * from posts")
List<PostEntity> findAll();
```

