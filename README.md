# Liverpool_player_list
アプリ概要
(2000年以降にリバプールに所属した選手が分かるアプリ)

## 制作背景
サッカーが好きでよくネットで試合を観戦するのですが、
「あれ？この選手このチームにいるんだっけ？」や「あの選手今どこにいるんだろう？」
と感じる瞬間があります。
そこで自分がサッカーを見始めた2000年以降に
好きなチームのリバプールに所属した選手が分かるアプリを作成しようと思いました。

## DEMO(gifで動画や写真を貼って、ビューのイメージを掴んでもらいます)
　⇒できている範囲で貼り付けましょう。

## 実装予定の内容
### DB設計　

## usersテーブル
|------|----|-------|
|id               |integer    |null:false,unique:true| 
|nickname         |string     |null:false|
|favarite_player  |integer    |null:false|enum| select|
|introduction     |text|   
|password         |

### Association
- has_one :player

## playersテーブル

|Column|Type|Options|
|------|----|-------|
|id         |integer    |null:false,unique:true| 
|first_name |string     |null:false|
|last_name  |string     |null:false|
|position   |integer    |null:false|enum| select
|birthday   |integer    |null:false|
|belongs    |integer    |null:false|
|picture    |integer    |null:false|


### Association
- has_many: :games
- has_many: :player_games
- has_one:  :player_picture

## gamesテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null:false, unique:true|
|home-player-1|
|home-player-2|
|home-player-3|
|home-player-4|
|home-player-5|
|home-player-6|
|home-player-7|
|home-player-8|
|home-player-9|
|home-player-10|
|home-player-11|
|bench-player-1|
|bench-player-2|
|bench-player-3|
|bench-player-4|
|bench-player-5|
|home_score|
|away_score|


### Asociation
- has_many: :players
- has_many: :player_games
- has_many: :coach_games



## coachsテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null:false,unique:true|
|first_name|string|null:false,index:true| 
|last_name|integer|null:false|
|birthday|
|belongs|

### Association
- has_many: :games
- has_many: :coach_games
- has_one:  :coach_picture

## player_picturesテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null:false, unique:true|   
|image|string|null:false|
|player_id|references|null:false, foreign_key:true|

### Association
- belongs_to :player

## coach_picturesテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null:false, unique:true|   
|image|string|null:false|
|coach_id|references|null:false, foreign_key:true|

### Association
- belongs_to :player

