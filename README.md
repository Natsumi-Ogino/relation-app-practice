# relation-app-practice

## 概要
COACHTECH 教材 Tutorial 9-5「リレーション ハンズオン演習」で作成した成果物である。
投稿(Post)にコメント(Comment)とタグ(Tag)を関連付けた、閲覧専用のブログシステムである。
1対多・多対多のリレーションを実装し、Eager Loadingやリレーションを使った絞り込み検索を実践した。

## 使用技術
- PHP 8.x
- Laravel 10.x
- Eloquent ORM（hasMany / belongsTo / belongsToMany）
- MySQL
- Laravel Sail（Docker）
- Git / GitHub

## 学んだこと
- Eager Loading（`with`）を使うことでN+1問題(データを取得するたびにクエリが何度も発行されてしまう問題)を防げることを学んだ。
- 中間テーブル（`post_tag`）を用いた多対多リレーション（`belongsToMany`）の実装方法を理解した。
- Tinkerでのテストデータ作成では複数行にまたがる`create()`の書き方で改行するとエラーになる場面があり、1行にまとめて書く必要があることを学んだ。

## 動作確認
`sail up -d` で環境を起動し`http://localhost/posts` にアクセスすると投稿一覧が表示される。
投稿タイトルをクリックすると詳細ページに遷移し、タグをクリックするとそのタグが付いた投稿だけに絞り込まれる。