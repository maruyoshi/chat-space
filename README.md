# README

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false, unique: true|
|password|string|null: false|

### Association
- has_many :messages
- has_many :groups, through: :group_users
- has_many :group_users

## massagesテーブル

|Column|Type|Options|
|------|----|-------|
|content|string|　|
|image|string|　|
|user_id|references :user|foreign_key: true|
|group_id|references :group|foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :messages
- has_many :users, through: :group_users
- has_many :group_users


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|references :user|foreign_key: true|
|group_id|references :group|foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
