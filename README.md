## Tables
- optionについて
  - null : NOT NULL制約を実装
  - foreign_key : 外部キー制約を実装
  - add_index : インデックスを貼る 

### Users
|Column|Type|Options|
|------|----|-------|
|name|string|null:false|

### Groups
|Column|Type|Options|
|------|----|-------|
|name|string|null:false|

### Users_Groups
|Column|Type|Options|
|------|----|-------|
|user|references|null:false, foreign_key|
|group|references|null:false, foreign_key|

### Messages
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|text||
|user|references|null:false, foreign_key|
|group|references|null:false, foreign_key|

## Association
### Usres 
- has_many :Messages
- has_many :Groups, through: :Users_Group

### Groups
- has_many :Messages
- has_many :Users, through: :Users_Group

### Users_Groups
- belongs_to :User
- belongs_to :Group

### Messages
- belongs_to :User
- belongs_to :Group