# README

# この WEB アプリは店舗間の在庫共有アプリです。

# 店舗に不要な在庫を登録しておくことで欲しい店が名乗り出てくれるかも知れません。

# 逆に欲しい商品を登録しておくことも可能です。（期限を設ける）

# DB 設計

## stores テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| number   | string | null: false |
| password | string | null: false |
| name     | string | null: false |

### Association

- has_many :posts
- has_many :

## merchandises テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| JAN      | string | null: false |
| name     | string | null: false |
| quantity | string | null: false |

### Association

## comment テーブル
