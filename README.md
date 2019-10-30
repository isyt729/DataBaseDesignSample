## Tables
- optionについて
  - null : NOT NULL制約を実装
  - unique : 一意性制約を実装
  - foreign_key : 外部キー制約を実装
  - add_index : インデックスを貼る 

### Users
|Column|Type|Options|
|------|----|-------|
|name|string|null|

### Groups
|Column|Type|Options|
|------|----|-------|
|name|string|null|

### Users_Groups
|Column|Type|Options|
|------|----|-------|
|user_id|references|null, unique, foreign_key|
|group_id|references|null, unique, foreign_key|

### Messages
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|text||
|user|references|null, foreign_key|
|group|references|null, foreign_key|

## Association
### Usres 
- has_many :Messages
- belongs_to :Group, through: :Users_Group

### Groups
- has_many :Messages
- belongs_to :User, through: :Users_Group

### Users_Groups
- belongs_to :User
- belongs_to :Group

### Messages
- belongs_to :User
- belongs_to :Group