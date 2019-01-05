# README

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name  |string|index: true, null: false, unique: true|
|email |string|null: false, unique: true|

### Association
has_many :messages
has_many :groups, through: :members
has_many :members

## membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|reference|foreign_key: true|
|group_id|reference|foreign_key: true|

### Association
belongs_to :user
belomgs_to :group

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name  |string|null: false, unique: true|

### Association
has_many :users, through: :members
has_many :members
has_many :messages

## messageテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|reference|null: false, foreign_key: true|
|group_id|reference|null: false, foreign_key: true|
|content|text|
|image  |text|

### Association
belongs_to :group
belongs_to :user




