# ChatSpace DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
### Association
- has_many :posts
- has_many :comments

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|text|null: false|
|group_member|text|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|null: false|
|group_id|integer|null: false|
|user_id|integer|null: false|
### Association
- belong_to :user
- belong_to :group
- has_many  :posts,  through:  :posts_tags

