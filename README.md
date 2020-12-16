# テーブル設計

##　usersテーブル

| Column    | Type   | Options     |
| --------  | ------ | ----------- |
| email     | string | NOT: NULL   |
| password  | string | NOT: NULL   |
| name      | string | NOT: NULL   |
| profile   | text   | NOT: NULL   |
| occupation| text   | NOT: NULL   |
| position  | text   | NOT: NULL   |

### Association

- has_many : comments
- has_many : prototypes

##　commentsテーブル

| Column    | Type       | Options     |
| --------  | ------     | ----------- |
| text      | text       | NOT: NULL   |
| password  | references | foreign_key: true            |
| name      | references | foreign_key: true            |

### Association

- belongs_to : user
- belongs_to : prototype

## prototypesテーブル

| Column    | Type       | Options     |
| --------  | ------     | ----------- |
| title     | string     | NOT: NULL   |
| catch     | text       | NOT: NULL   |
| concept   | text       | NOT: NULL   |
| user      | references | foreign_key: true |

## Association

- belongs_to : user
- has_many : comments