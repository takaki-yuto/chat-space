# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

## usersテーブル
|column|Type|Options|
|------|----|-------|
|name|text|null: false|
|email|text|null: false, unique: true|
|pass|text|null: false|

### Association
- has_many :groups, through: :groups_users
- has_many :messages
- has_many :groups_users

## groupsテーブル
|column|Type|Options|
|------|----|-------|
|name|text|null: false|

### Association
- has_many :users, through: :groups_users
- has_many :messages
- has_many :groups_users

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## messagesテーブル
|column|Type|Options|
|------|----|-------|
|body|text|null:false|
|image|text|null:false|
|group_id|integer|null:false, foreign_key:true|
|user_id|integer|null:false, foreign_key:true|

### Association
- belongs_to :user
- has_many :groups

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
