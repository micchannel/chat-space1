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


## usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|nickname|string|null: false, foreign_key: true|
|email|string|null: false, foreign_key: true|
|password|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|message|string|null: false, foreign_key: true|

### Association
- has_one :user_id
- has_one :nickname
- has_one :email
- has_one :password
- belongs_to :group
- has_many :message


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_name|string|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- has_many :user
- has_one :group_name
- has_one :group_id

 
## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## messageテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
