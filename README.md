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


## usersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|user_name|text|null: false|

### Association

  has_many :users_groups
  has_many :users, through: :users_groups

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group|references|null: false, foreign_key: true|
|group_name|text|null: false|

### Association

  has_many :users_groups
  has_many :groups, through: :users_groups

## users_groupsテーブル

|Column|Type|Options|
|------|----|-------|
|id|references|null: false, foreign_key: true|
|users_id|integer|null: false|
|groups_id|integer|null: false|

### Association

- belongs_to :group
- belongs_to :user

## commentsテーブル

|Column|Type|Options|
|------|----|-------|
|id|references|null: false, foreign_key: true|
|user_id|integer|null: false|
|group_id|integer|null: false|
|body|text|null: false|
|image|string||

### Association

- belongs_to :user