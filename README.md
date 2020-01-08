# db-test
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false|
### Association
- has_many :group_users
- has_many :messages
- has_many :groups through: :groups_users
## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :groups users
- has_many :messages
- has_many :users through: :groups_users
## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|message|text||
|image|string||
|users|references|null: false, foreign_key: true|
|groups|references|null: false, foreign_key: true|
### Association
- belongs_to :groups
- belongs_to :users
## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|users|references|null: false, foreign_key: true|
|groups|references|null: false, foreign_key: true|
### Association
- belongs_to :groups
- belongs_to :users
