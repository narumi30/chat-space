
## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, foreign_key: true|
|password|string|null: false, foreign_key: true|
|mail|string|null: false, foreign_key: true|

### Association
- has_many :groups, through: groups_users
- has_many :messages
- has_many :groups_users


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

## Association
- has_many :users, through: groups_users
- has_many :messages
- has_many :groups_users


## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|groups_id|integer|null: false, foreign_key: true|
|image|string| |
|text|string| |

## Association
- belongs_to :user
- belongs_to :group


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user