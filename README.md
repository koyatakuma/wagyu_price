# Git Lesson

## リモートリポジトリとローカルリポジトリとはそれぞれ何でしょうか？

#### リポジトリとは
ファイル、プログラム、設定情報などの情報が保管されているデータベースのことを指す。
#### リモートリポジトリ
専用のサーバに配置して複数人で共有するためのリポジトリ
ネット上にファイルをアップロードした状態でファイル管理するもの。
使用されている代表的なプラットフォームにGitHub、BitBucket、Assembla、GitLabなどが挙げられる。
#### ローカルリポジトリ
自分の手元のパソコン上でバージョン管理するため作成したリポジトリ。

## プッシュとマージの違いは何でしょうか？
#### プッシュ
ローカルリポジトリで行なった編集内容をリモートリポジトリに上書きすること。
#### マージ
各ブランチにて行なった変更内容をひとつに結合すること。


## コミットとプッシュの違い
#### コミット
ローカルリポジトリに変更を反映すること。
#### プッシュ
リモートリポジトリに変更を反映すること。
>コミットはローカル上でgit addでステージングしたファイルの保存を確定すること。プッシュはコミットされたファイルをリモートリポジトリに反映、同期させること。


## コミットのメッセージはどのように書いてあげるのが最適でしょうか？
- 誰が見ても一目で変更内容がわかるようなものにすること
- 各チームやプロジェクトのルールに従ったメッセージを残すこと
- 一行目にはprefix (接頭辞)をつけるとわかりやすいものになる

> 例）
1行目：コミット内容の要約（タイトル・概要）
2行目：空行
3行目以降：本文 （内容・詳細・変更理由）

**prefixの例**
fix	バグ修正
クリティカルなバグ修正なら hotfix
add
feat	新規機能・新規ファイル追加
feat は feature の略
update	バグではない機能修正
change	仕様変更による機能修正
clean
refactor
improve	整理 (リファクタリング等)
disable	無効化 (コメントアウト等)
remove
delete	ファイル削除、コードの一部を取り除く
rename	ファイル名の変更
move	ファイル移動
upgrade	バージョンアップ
revert	修正取り消し
docs	ドキュメントのみ修正
style	空白、セミコロン、行、コーディングフォーマットなどの修正
perf	性能向上する修正
perf は perfomance の略
test	テスト追加や間違っていたテストの修正
chore	ビルドツールやライブラリで自動生成されたものをコミットするとき

## ローカルでマージするフローと、プルリクエストでマージするフローの違いは何でしょうか？

#### ローカルにてマージするフローの場合

**メリット**
- プルリクエストでマージする方法に比べ時間がかからない

**デメリット**
- 第三者にてコードを確認することができない
- 自分以外にコードを確認されないまま変更を行なうため意図しないバグにつながる可能性がある
- チームでの開発には向かない

#### プルリクエストでマージを行なうフロー場合
**メリット**
- 変更内容を確認後masterブランチへマージを行なうためマージ前に第三者にて変更内容をかくにんすることができる
- 作成されたプルリクエストは一覧で見ることができるため、未完了のプルリクエストを簡単に確認することができる
- プルリクエスト作成者とレビュー担当者の間でプルリクエスト上でコメントをやり取りし議論を重ねることができる
- 必要に応じて対象のブランチに何度でも変更をコミット・プッシュすれば自動的にプルリクエスト上に反映される

**デメリット**
- 時間がかかる

>バグの発生を抑えるためmasterブランチに変更を加える際は第三者からのコードレビューが必要である。

## コンフリクトを起こしてしまった場合、どう対処すべきですか？
#### コンフリクトとは
>それぞれのブランチにて同じ箇所に別の変更が加わったときにGitがどちらの変更を採用すべきか判断できずmergeが中断されてしまうこと。

自分以外の人が書いたソースコードの内容を把握する、少しでも意図が読み取れない場合相談をしながら慎重に作業を進める必要がある。
