## Tbales
### Users
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, foreign_key: false|
|name|string|null: false, foreign_key: false|
|mail_address|string|null: false, foreign_key: false|
|password|string|null: false, foreign_key: false|

### Groups
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, foreign_key: false|
|name|string|null: false, foreign_key: false|

### Users_Groups
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, foreign_key: false|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Messages
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, foreign_key: false|
|body|text|null: false, foreign_key: false
|image|text|null: true, foreign_key: false|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

## Association
### Usres 
- has_many :messages
- belongs_to :Users_Groups

### Groups
- has_many :messages
- belongs_to :Users_Groups

### Users_Groups
- has_many :users
- has_many :groups

### Messages
- belongs_to :users
- belongs_to :groups
