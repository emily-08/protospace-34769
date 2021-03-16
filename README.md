# テーブル設計

## usersテーブル

| Colmn      | Type        | Options      |
|:-----------|------------:|:------------:|
| email      | string      | null: false  |
| password   | string      | null: false  |
| name       | string      | null: false  |
| profile    | text        | null: false  |
| occupation | text        | null: false  |
| position   | text        | null: false  |

### Association

- has_many :prototypes
- has_many :comments

## prototypesテーブル

| Colmn      | Type        | Options      |
|:-----------|------------:|:------------:|
| title      | string      | null: false  |
| cath_copy  | text        | null: false  |
| concept    | text        | null: false  |
| user       | references  | null: false  |

### Association

- belongs_to :user
- has_many :comments

## commentsテーブル

| Colmn      | Type        | Options      |
|:-----------|------------:|:------------:|
| text       | text        | null: false  |
| user       | references  |              |
| prototype  | references  |              |

### Association

- belongs_to :user
- belongs_to :prototype