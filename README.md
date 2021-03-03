# README

# アプリケーション名
anilive

# アプリケーション概要
アニメ、声優について話し合えるアプリです

実装機能は以下の通りです

・投稿一覧表示機能
・投稿投稿機能
・投稿削除機能
・投稿編集機能
・投稿詳細表示機能
・ユーザー登録/ログイン機能
・投稿へのコメント機能
・投稿検索機能

使用言語
・Ruby
・Ruby on rails
・HTML
・CSS
・JavaScript

# アプリケーションのURL


# 制作背景
好きなアニメ、声優を好きな人同士で語り合えるためです。（別にアニメ以外のものを投稿可）
私自身アニメ、声優が好きということもありこのような機能を持ったアプリケーションがあればとても
便利だと感じて作成しました。
写真付投稿をしてこのキャラクター、声優が好きなど意見を言い合えるようにコメント機能をつけました。
検索機能で自分と共通した趣味を持つ人物とのコメントで話を盛り上げることができます。

## users テーブル

| Column   | Type   | Options                   |
| -------- | ------ | ------------------------- |
| nickname               | string |             |
| email                  | string | null: false |
| encrypted_password     | string | null: false |

### Association

- has_many :tweets
- has_many :comments

## tweets テーブル

| Column | Type   | Options     |
| ------ | ------ | ----------- |
| text   | string |             |
| image  | text   |             |

### Association

- belongs_to :user
- has_many :comments

## comments テーブル

| Column | Type      | Options |
| -------- | ------- | ------- |
| user_id  | integer |         |
| tweet_id | integer |         |
| text     | text    |         |

### Association

- belongs_to :tweet
- belongs_to :user
