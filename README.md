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

## userテーブル

|Column|Type|Options|
|------|----|-------|
|user_name|string|null: false|
|email|string|null: false|
|password|string|null: false|
|groups|string|null: false|
|messages|string||

### Association
- has_many :messages
- has_many :groups

-----------------------
-----------------------

## groupテーブル

|Column|Type|Options|
|------|----|-------|
|users|string|null: false|
|messages|text|null: false|


### Association
- has_many :users
- has_many :messages

-----------------------
-----------------------


## messageテーブル

|Column|Type|Options|
|------|----|-------|
|user|string|null: false|
|group|string|null: false|

### Association
- belongs_to :user
- belongs_to :group

-----------------------
-----------------------


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

-----------------------
-----------------------

## 