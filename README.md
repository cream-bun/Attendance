# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

## user_administrator テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| encrypted_password | string | null: false |

### Association

- has_many :room_users
- has_many :rooms, through: :room_users
- has_many :messages

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| student_number     | string | null: false |
| department         | string | null: false |
| name               | string | null: false |
| encrypted_password | string | null: false |

### Association

- has_many :room_users
- has_many :users, through: :room_users
- has_many :messages

## attendance テーブル

| Column          | Type   | Options                        |
| --------------- | ------ | ------------------------------ |
| attendance      | string |                                |
| student_id


### Association

- belongs_to :room
- belongs_to :user

## Question テーブル

| Column         | Type   | Options                        |
| -------------- | ------ | ------------------------------ |
| question       | text   |                                |

### Association

- belongs_to :room
- belongs_to :user


## answer テーブル

| Column         | Type    | Options                        |
| -------------- | ------- | ------------------------------ |
| answer         | integer |                                |

### Association

- belongs_to :room
- belongs_to :user


## lecture テーブル

| Column         | Type    | Options                        |
| -------------- | ------- | ------------------------------ |
| date           | date    |                                |
| student_id 
| question_id 

### Association

- belongs_to :room
- belongs_to :user

