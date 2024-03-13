# テーブル設計

## usersテーブル

| Column             | Type   | Options     |
|--------------------|--------|-------------|
| nickname           | string | null: false |
| username           | string | null: false |
| encrypted_password | string | null: false |

### Association

-has_many :plans

## plansテーブル

| Column        | Type       | Options                        |
|---------------|------------|--------------------------------|
| name          | string     | null: false                    |
| team          | references | null: false, foreign_key: true |
| opponent_team | references | null: false, foreign_key: true |
| user          | references | null: false, foreign_key: true |

### Association

-has_one :team
-has_one :opponent_team

## teamsテーブル

| Column    | Type       | Options                        |
|-----------|------------|--------------------------------|
| name      | string     | null: false                    |
| z1_player | integer    | null: false                    |
| z2_player | integer    | null: false                    |
| z3_player | integer    | null: false                    |
| z4_player | integer    | null: false                    |
| z5_player | integer    | null: false                    |
| z6_player | integer    | null: false                    |
| plan      | references | null: false, foreign_key: true |

### Association

-belongs_to :plan

## opponent_teamsテーブル

| Column    | Type       | Options                        |
|-----------|------------|--------------------------------|
| name      | string     | null: false                    |
| z1_player | integer    | null: false                    |
| z2_player | integer    | null: false                    |
| z3_player | integer    | null: false                    |
| z4_player | integer    | null: false                    |
| z5_player | integer    | null: false                    |
| z6_player | integer    | null: false                    |
| plan      | references | null: false, foreign_key: true |

### Association

-belongs_to :plan