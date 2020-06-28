# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation  
  groups_usersテーブル  
|Column|Type|Options|  
|------|----|-------|  
|user|references|null: false, foreign_key: true|  
|group|references|null: false, foreign_key: true|  

  Association  
- belongs_to :group  
- belongs_to :user  

  usersテーブル  
  |Column|Type|Options|  
  |------|----|-------|  
  |name|string|null: false, index: true|  
  Association  
- has_many :messages  
- has_many :groups_users  
- has_many :groups, through: :groups_users  

  messagesテーブル  
  |Column|Type|Option|  
  |------|----|------|  
  |image|string||  
  |text|text||  
  |user|references|null: false,foreign_key: true|  
  |group|references|null: false, foreign_key: true|  
  Association  
  - belongs_to :user  
  - belongs_to :group  

  groupsテーブル  
  |Column|Type|Options|  
  |------|----|-------|  
  |name|string|null: false|  
  Association  
  - has_many :groups_users  
  - has_many :users, through: :groups_users  
  - has_many :messages  
  






* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
