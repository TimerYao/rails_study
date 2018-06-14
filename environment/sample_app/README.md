# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
3.2.1 练习
1. 生成含有 bar 和 baz 两个动作的 Foo 控制器；
    rails generate controller Foo bar baz
2. 使用旁注 3.1 中介绍的技术删除 Foo 控制器及相关的动作。
    rails destroy controller Foo bar baz

    本章所学：
        命令生产控制器（rails generate controller ControllerName <optional action names> ），
        定义路由，rails 静态html及嵌入式ruby（主要是provide 和yield方法，实现title动态和不重复）
        遇红-变绿-重构 步骤的 测试(rails test 命令)