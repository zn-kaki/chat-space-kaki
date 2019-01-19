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

## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|foreign_key :true|
|group_id|integer|foreign_key :true|

### Association
- belongs_to :user
- belongs_to :group

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|mail|string|null: false|
|password|string|null: false|

### Association
- has_many :groups, through: members
- has_many :messages
- has_many :members

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
-has_many :messages
-has_many :users, through: :members
-has_many :members

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|text||text||
|image|text||
|user_id|integer|foreign_key: true|
|group_id|integer|foreign_key: true|

### Association
-belongs_to :user
-belongs_to :group



