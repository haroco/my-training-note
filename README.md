## usersテーブル

|Column     |Type       |Options         |
|-----------|-----------|----------------|
|name       |string     |null: false     |
|encrypted_password|string|null:false    |


### Association
has_many :trainings
has_many :training_records




## trainingsテーブル

|Column     |Type       |Options         |
|-----------|-----------|----------------|
|training_name       |string     |null: false     |
|description         |text       |                |
|how_to              |text       |                |
|memo                |text       |                |
|user                |references |null: false, foreign_key: true     |
|category            |references |null: false, foreign_key: true     |


### Association
belongs_to :user
belongs_to :category
has_many :training_records




## categoriesテーブル

|Column     |Type       |Options         |
|-----------|-----------|----------------|
|genre      |string     |null: false     |


### Association
has_many :trainings



## training_recordsテーブル

|Column     |Type       |Options         |
|-----------|-----------|----------------|
|user_id             |references     |null: false, foreign_key: true     |
|training_id         |references     |null: false, foreign_key: true     |
|date                |date           |null: false                        |
|comment             |text           |                                   |


### Association
belongs_to :user
belongs_to :training