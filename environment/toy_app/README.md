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
# 
2.2.1 练习
创建新用户时，刷新页面后成功消息清空；
只填写名字也可创建成功；
邮箱格式错误也可创建成功；
提示：User was successfully destroyed.

2.2.2 练习

1. 参照图 2.11，写出访问 /users/1/edit 页面的步骤
    1. 点击编辑，浏览器向 /users 发送请求，展示出用户编辑页面；
    2. 输入新的信息后，Rails 的路由把 /users 交给 Users 控制器的 update 动作处理；
    3. update 动作向表单提交信息；
    4. 更新成功返回信息给控制器的show动作；
    5. 把当前用户赋值给 @users 变量，然后传入 show 视图；
    6. 视图使用嵌入式 Ruby 把页面渲染成 HTML；
    7. 控制器把 HTML 送回浏览器。

2. 在脚手架生成的代码中找出前一题从数据库中检索用户的代码
3. 编辑用户页面的视图文件，其名称是什么？
 edit.html.erb

2.3.1 练习

1. （如果你了解 CSS）发布一篇新微博，然后使用浏览器中的 HTML 审查工具找出“Micropost was successfully created.”文本的 CSS ID。刷新页面后会发生什么？
    消息清空；
2. 发布微博时不输入内容也不指定用户 ID 试试。
    成功；
3. 发布一篇内容超过 140 字（例如维基百科中介绍 Ruby 的第一段）的微博试试。
  成功；
4. 删除前几题创建的微博。
    提示：User was successfully destroyed.且更新当前页面
2.3.2 练习
1. 使用前一节练习中的那段文字发布微博，这一次有什么变化呢？
   错误信息：Content is too long (maximum is 140 characters)
2. 使用浏览器中的 HTML 审查工具找到前一题那个错误消息的 CSS ID
   error_explanation


2.3.3
1. 编辑显示用户的页面，显示用户发布的第一篇微博。（根据文件中的其他内容猜测所需的句法。）访
问 /users/1，确认改动是正确的。
2. 代码清单 2.16 添加了一个存在性验证，确保微博的内容不能为空。确认这个验证的行为与图 2.16 中一
样。
3. 把代码清单 2.17 中的 FILL_IN 换成相应的代码，为 User 模型的 name 和 email 属性添加存在性验证。
效果如图 2.17 所示。
class User < ApplicationRecord
    has_many :microposts
    validates :name, presence: true   #   把 FILL_IN 换成正确的代码
    validates :email, presence: true #   把 FILL_IN  换成正确的代码
end

2.3.4

1. 查看 Application 控制器文件的内容，找出 ApplicationController 继承自 ActionController::Base 的
代码。
    class ApplicationController < ActionController::Base
    protect_from_forgery with: :exception
    def hello
        render html: "hello world!"
    end
    end

2. ApplicationRecord 是不是也在类似的文件中继承 ActiveRecord::Base？提示：可能是 app/models 目录
中名为 application_record.rb 的文件

    class ApplicationRecord < ActiveRecord::Base
    self.abstract_class = true
    end