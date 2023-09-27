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

# コントローラーの変更する
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

