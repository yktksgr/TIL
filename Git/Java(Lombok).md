# MySQLとの連携

ライブラリ名 |	機能 |
--- | ---- |
MySQL Driver	|  JavaからMySQLを操作するためのライブラリ
MyBatis	| SQL文の発行を、Javaのメソッドとして定義できるようにするライブラリ
Lombok |	コードの記述を簡略化するためのライブラリ

build.gradle　に下記のように入力する
```java
dependencies {
    ~省略〜
    implementation 'org.mybatis.spring.boot:mybatis-spring-boot-starter:2.2.2'
    runtimeOnly 'mysql:mysql-connector-java'
    compileOnly 'org.projectlombok:lombok'
    annotationProcessor 'org.projectlombok:lombok'
}
```

