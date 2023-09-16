# アノテーション
アノテーションは「注釈」という意味を持つ英単語で、Javaにおいて非常に重要な機能を持つ。

アノテーションは、クラスやメソッドに特別な意味を持たせるための機能。

```Java
@Controller
public class PostController {
    @GetMapping("/hello")
    @ResponseBody
    public String showHello(){
        return "<h1>Hello World!</h1>";
    }
}
```
---

# @Controller

@Controllerは、そのクラスがコントローラーであることをSpringに伝えるためのアノテーション

Railsでは、「rails g controller」というコマンドを実行することでコントローラーを作成。それに対してSpringでは、クラス定義の直前に「@Controller」と記述することで、クラスがコントローラーとして扱われる。

# @GetMapping

GetMappingは、ブラウザで入力されたURLと、実行されるメソッドを紐づけるためのアノテーション

Railsでは、routes.rbファイルに以下の記述を行うことで、「/post」というURLと「Postsコントローラーのindexアクション」を関連づけていた。


```Ruby
get 'posts', to: 'posts#index'
```
@Mappingは、このRailsのルーティングと同様の機能。

メソッドの前に、「@GetMapping("/hello")」というアノテーションをつけることで、URLに「（アプリのルートパス）/hello」と入力された場合、そのメソッドが実行されるようになる

# @ResponseBody

@ResponseBodyは、ブラウザからのリクエストに対して、直接HTMLを返す際に利用するアノテーション

---
# @PathVariable

@PathVariableは、URLに含まれるパラメータを受け取るためのアノテーション   
メソッド内で使用したい変数の前に、このアノテーションをつけることで受け取ることができます。

---
# Thymeleaf
Spring Bootにあるライブラリ

Railsでは、ERBというテンプレートエンジンを使用。  
ERBを使用することで、コントローラーとビューのコードを分離して管理しやすくしていた！

導入作業は、ルートディレクトリにある「build.gradle」ファイルに記述をする
```java
implementation 'org.springframework.boot:spring-boot-starter-thymeleaf'
```
