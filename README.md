# README
# この WEB アプリは店舗間の在庫共有アプリです。
# 店舗に不要な在庫を登録しておくことで欲しい店が名乗り出てくれるかも知れません。
# 逆に欲しい商品を登録しておくことも可能です。（期限を設ける）


# DB 設計

## storesテーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| number   | string | null: false |
| password | string | null: false |
| name     | string | null: false |

### Association

- has_many :items
- has_many :comments

## itemsテーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| jan_code | string | null: false |
| name     | string | null: false |
| quantity | string | null: false |
| store_id | string | null: false |

### Association

- belongs_to :store
- has_many :comments

## commentテーブル

| Column   | Type    | Options                        |
| -------- | ------- | ------------------------------ |
| text     | text    | null: false                    |
| store_id | integer | null: false, foreign_key: true |
| item_id  | integer | null: false, foreign_key: true |

### Association

- belongs_to :store
- belongs_to :item

## transactionテーブル

| Column   | Type    | Options                        |
| -------- | ------- | ------------------------------ |
| quantity | string  | null: false                    |
| item_id  | integer | null: false, foreign_key: true |
| buyer_id | integer | null: false, foreign_key: true |

### Association

- belongs_to :store
- belongs_to :item

## managerテーブル

| Column         | Type    | Options                        |
| -------------- | ------- | ------------------------------ |
| transaction_id | integer | null: false, foreign_key: true |

### Association

- belongs_to :transaction


