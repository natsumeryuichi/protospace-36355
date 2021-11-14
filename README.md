# README

#テーブルの設計

#usersテーブル

|        column        |  type    |          option          |
| -------------------- | -------- | ------------------------ |
|  email               |  string  |  null:false  unique:true |
|  encrypted_password  |  string  |  null:false              |
|  name                |  string  |  null:false              |
|  profile             |  text    |  null:false              |
|  occupation          |  text    |  null:false              |
|  position            |  text    |  null:false              |

#Association
- has_many :comments
- has_many :prototypes

#commentsテーブル

|      column       |     type     |             option             |
| ---------------- | ------------ | ------------------------------- |
|  content         |    text      |  null:false                     |
|  prototype       |  references  |  null:false  foreign_key: true  |
|  user            |  references  |  null:false  foreign_key: true  |

#Association
- belong_to :users
- belong_to :prototypes

#prototypesテーブル

|    column    |     type     |             option             |
| ------------ | ------------ | ------------------------------ |
|  title       |  string      |  null:false                    |
|  catch_copy  |  text        |  null:false                    |
|  concept     |  text        |  null:false                    |
|  user        |  references  |  null:false  foreign_key: true |

#Association
- belong_to :users
- has_many  :comments

