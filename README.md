## usersテーブル

|Column|Type|Options|
|------|----|-------|
|Email|string|null: false|
|Password|string|null: false|
|Name|string|null: false|
### Association
- has_many :messages
- has_many :groups


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|
### Association
- has_many :messages
- has_many :users


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user


## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|null: false|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user
