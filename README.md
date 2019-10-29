## Tables
- optionについて
  - null : NOT NULL制約を実装
  - unique : 一意性制約を実装
  - foreign_key : 外部キー制約を実装
  - add_index : インデックスを貼る 

### Users
|Column|Type|Options|
|------|----|-------|

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
|body|text|null|
|image|text||
|user_id|references|null, foreign_key|
|group_id|references|null, foreign_key|

## Association
### Usres 
- has_many :Messages
- has_many :Groups
- belongs_to :Users_Group, through: :Groups

### Groups
- has_many :Messages
- belongs_to :Users_Group, through: :Users
- belongs_to :User

### Users_Groups
- belongs_to :User
- belongs_to :Group

### Messages
- belongs_to :User
- belongs_to :Group