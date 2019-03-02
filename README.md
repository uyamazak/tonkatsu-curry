# 🍛とんかつカレーBBS 設置の手引き
とんかつカレーBBSはFirebaseとVue.jsを使った最新の実用性のないBBSです。

Google Cloud Console上だけで開発、デプロイができます。

閲覧、書き込みにはGoogleログインが必要なため完全な匿名ではありません。

## とんかつカレーBBS

## インストール 
Firebaseプロジェクト作ってCloud Shellで

`firebase login --no-localhost`

する。

`git clone {URL}`

する。できたディレクトリ内のfunctionsに入り

`cd functions`

`npm install`

する


## デプロイ

`firebase deploy`

プロジェクトを指定されてないエラーが出るときは追加しておく

`firebase use --add {ProjectID}`


## お皿（スレッド）の作り方
Firebaseコンソールを開き、Firestore (Database)で下記ドキュメントを任意のdishIDで作る

`/dishes/{dishID}`

ドキュメントに下記のデータを追加する

- フィールド: title, タイプ: string, 値: 皿タイトル
- フィールド: description, タイプ: string, 値: 説明文
- フィールド: timestamp, タイプ: timestamp, 値: 作成日時

下記URLでアクセスできる
`
https://{projectID}.firebaseapp.com/~{dishID}/
`

## 管理者の追加
 + Firebaseコンソールを開く
 + Authenticationで管理者にしたいユーザーのUIDをコピー
 + Database (Firestore）で下記ドキュメントを作る

`/users/{UID}`

作成したドキュメントに下記データを追加

- フィールド: isAdmin, タイプ: boolean, 値: true

## トラブルシューティング

### ストレージに書き込めない
Firebase Storageはプロジェクトで初めて使うとき初期化が必要な模様。
FirebaseコンソールでStorageを開き「スタートガイド」をクリックする