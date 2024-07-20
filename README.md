## usersテーブル
| Column              | Type       | Options                        |
| ------------------- | ---------- | ------------------------------ |
| nickname            | string     | null: false                    |
| email               | string     | null: false, unique: true      |
| encrypted_password  | string     | null: false                    |
| last_name           | string     | null: false                    |
| first_name          | string     | null: false                    |
| kana_last           | string     | null: false                    |
| kana_first          | string     | null: false                    |
| birth_year          | string     | null; false                    |
| birth_month         | string     | null; false                    |
| birth_day           | string     | null; false                    |

### Association
- has_many :items
- has_many :orders

## itemsテーブル
| Column         | Type       | Options                        |
| -------------- | ---------- | ------------------------------ |
| item_name      | text       | null: false                    |
| explanation    | text       | null: false                    |
| category       | string     | null: false                    |
| condition      | string     | null; false                    |
| charge_load    | string     | null; false                    |
| area           | string     | null; false                    |
| shipping_time  | string     | null; false                    |
| price          | integer    | null; false                    |
| condition      | references | null; false, foreign_key: true |

### Association
- belongs_to :user
- has_one :order

## ordersテーブル
| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| user      | references | null: false, foreign_key: true |
| item      | references | null; false, foreign_key: true |

### Association
- belongs_to :user
- belongs_to :iteme
- has_one :delivery


## ordersテーブル
| Column        | Type       | Options                        |
| ------------- | ---------- | ------------------------------ |
| post_number   | string     | null; false                    |
| prefecture    | string     | null; false                    |
| address       | string     | null; false                    |
| building      | string     | null; false                    |
| phone_number  | string     | null; false                    |
| order         | references | null; false, foreign_key: true |

### Association
- belongs_to :order