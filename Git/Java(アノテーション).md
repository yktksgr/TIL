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
