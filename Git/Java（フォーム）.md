# フォームの作成
Javaでフォームを利用するのは、Railsの場合と比べて若干複雑。   
フォームを表示するために３つのステップに分けて実装する。

① Formクラスを作成する   
② コントローラーを変更する   
③ ビューを作成する  

---

# Formクラスの作成
Formクラスとは、フォームに入力されたデータを格納するためのクラス

Railsの場合、フォームで入力されたデータを受け取るために、paramsというハッシュを利用。   
paramsはRailsによって自動的に生成され、コントローラー内で参照することによりユーザーの入力を保存。

このparamsに代わるものとして、JavaではFormクラスを自前で作成する！

---

# コントローラーの変更
```java
~省略
@GetMapping("/postForm")
    public String showPostForm(@ModelAttribute("postForm") PostForm form){
        return "postForm";
    }

```
@ModelAttribute/このアノテーションを使用すると、任意のデータをModel型のオブジェクト内に格納可能になる。

Spring Bootでは、このModel型のオブジェクトは特別な意味を持っており、データの一時保管場所のように活用できる。

コントローラーでこの保管場所にデータを保管しておき、それをビューで呼び出すという使い方となる。

詳しく・・・
```Java
@ModelAttribute("呼び出すときの名称") 保存したい変数のデータ型　保存したい変数
```
このコードによって、PostForm型の変数formを登録し、後で「postForm」という名称で呼び出せる。

---
# ビューの作成
一例として・・・
```java
<form action="#" th:action="@{/posts}" th:method="post" th:object="${postForm}">
```
Thymeleafを使って３つの指定をおこなっている。

th:action="@{/posts}"は、フォームで投稿が行われた際に、次にアクセスするURLを指定するための記述。   
（ここでは、/postsを指定。）

th:method="post"は、フォームで投稿が行われた際に送信するHTTPメソッドを指定.   
今回はは投稿機能を実装のため、HTTPメソッドはPOSTを使用。

th:object="${postForm}"は、フォームの投稿内容を紐づけるFormクラスを指定するためのもの。   
この記述により、コントローラーで設定したpostFormとフォームを紐づけている。

