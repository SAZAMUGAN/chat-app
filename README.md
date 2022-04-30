# テーブル設計

<!-- usersテーブル -->
| Column             | Type  | Options      |
| ------------------ | ----- | ------------ |
| name               | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |
 
 <!-- Association -->
- has_many :room_users
- has_many :rooms, through: :room_users
- has_many :messages



<!-- roomsテーブル -->
| Column             | Type  | Options      |
| ------------------ | ----- | ------------ |
| name               | string | null: false |

<!-- Association -->
- has_many :room_users
- has_many :users, through: :room_users
- has_many :messages



<!-- room_usersテーブル -->
| Column             | Type  | Options      |
| ------------------ | ----- | ------------ |
| user               | string | null: false, foreign_key: true |
| room               | string | null: false, foreign_key: true |

<!-- Association -->
- belongs_to :room
- belongs_to :user



<!-- messagesテーブル -->
| Column             | Type  | Options      |
| ------------------ | ----- | ------------ |
| content            | string | null: false, foreign_key: true |
| user               | string | null: false, foreign_key: true |
| room               | string | null: false, foreign_key: true |

- belongs_to :room
- belongs_to :user



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
