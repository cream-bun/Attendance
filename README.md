# README

## user_admins テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| encrypted_password | string | null: false |



## students テーブル

| Column             | Type   | Options                        |
| ------------------ | ------ | -------------------------------|
| student_number     | string | null: false                    |
| department         | string | null: false                    |
| name               | string | null: false                    |
| birth_day          | date   | null: false                    |
| encrypted_password | string | null: false                    |


### Association

- has_many :answer
- has_many :lectures, through: :attendances



## lectures テーブル

| Column         | Type    | Options                        |
| -------------- | ------- | ------------------------------ |
| subject        | string  | null: false                    |

### Association

- has_many :students, through: :attendances


## attendances テーブル

| Column          | Type       | Options                        |
| --------------- | ---------- | ------------------------------ |
| dating          | date       | null: false                    |
| attendance      | string     | null: false                    |
| student         | references | null: false, foreign_key: true |
| lecture         | references | null: false, foreign_key: true |


### Association

- belongs_to :lecture
- belongs_to :student



## questions テーブル

| Column         | Type       | Options                        |
| -------------- | ---------- | ------------------------------ |
| dating         | date       | null: false                    |
| question       | text       |                                |
| lecture        | references | null: false, foreign_key: true |

### Association

- has_many :answers
- belongs_to :lecture


## answers テーブル

| Column         | Type       | Options                        |
| -------------- | ---------- | ------------------------------ |
| student        | references | null: false, foreign_key: true |
| question       | references | null: false, foreign_key: true |
| check          | boolean    | null: false                    |
| remarks        | text       |                                |

### Association
- belongs_to :student
- belongs_to :question





