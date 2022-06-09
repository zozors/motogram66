## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| email              | string | null: false |
| encrypted_password | string | null: false |
| nickname           | string | null: false |

# association
has_many :tweets
has_many :comments

## tweets テーブル

| Column             | Type        | Options     |
| ------------------ | ----------- | ----------- |
| image              | string      | null: false |
| text               | text        | null: false |
| user               | references  | null: false |

# association
belongs_to :user
has_many :comments

## comments　テーブル

| Column             | Type        | Options     |
| ------------------ | ----------- | ----------- |
| text               | text        | null: false |
| tweet              | references  | null: false |
| user               | references  | null: false |

# association
belongs_to :tweet
belongs_to :user
