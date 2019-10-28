## Tables
- optionについて
  - null : trueの場合、NOT NULL制約を実装
  - unique : trueの場合、一意性制約を実装
  - foreign_key : trueの場合、外部キー制約を実装
  - add_index : trueの場合、インデックスを貼る 
### Users
|Column|Type|Options|
|------|----|-------|
|id|integer|null: true, unique : true, foreign_key: false, add_index: false|
|name|string|null: true, unique : false, foreign_key: false, add_index: true|
|mail_address|string|null: true, unique : false, foreign_key: false, add_index: false|
|password|string|null: true, unique : false, foreign_key: false, add_index: false|

### Groups
|Column|Type|Options|
|------|----|-------|
|id|integer|null: true, unique : true, foreign_key: false, add_index: false|
|name|string|null: true, unique : false, foreign_key: false, add_index: false|

### Users_Groups
|Column|Type|Options|
|------|----|-------|
|id|integer|null: true, unique : true, foreign_key: false, add_index: false|
|user_id|references|null: true, unique : false, foreign_key: true, add_index: false|
|group_id|references|null: true, unique : false, foreign_key: true, add_index: false|

### Messages
|Column|Type|Options|
|------|----|-------|
|id|integer|null: true, unique : true, foreign_key: false, add_index: false|
|body|text|null: true, unique : false, foreign_key: false, add_index: false|
|image|text|null: false, unique : false, foreign_key: false, add_index: false|
|user_id|references|null: true, unique : false, foreign_key: true, add_index: false|
|group_id|references|null: true, unique : false, foreign_key: true, add_index: false|

## Association
### Usres 
- has_many :Messages
- belongs_to :Users_Groups

### Groups
- has_many :Messages
- belongs_to :Users_Groups

### Users_Groups
- has_many :Users
- has_many :Groups

### Messages
- belongs_to :Users
- belongs_to :Groups
