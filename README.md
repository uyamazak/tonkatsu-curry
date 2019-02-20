# 🍛とんかつカレーチャット設置の手引き
全部GCP Cloud Shell上で開発してます。

## インストール 
Firebaseプロジェクト作ってCloud Shellで

`firebase login --no-localhost`

する。

`git clone`

する。できたディレクトリ内のfunctionsに入り

`cd functions`

`npm install`

する

`firebase deploy`
する

## お皿（スレッド）の作り方
Fires0toreで下記ドキュメントを作る

`/dishes/{ID}`

ドキュメントに下記のデータを追加する

- フィールド: title, タイプ: string, 値: 皿タイトル
- フィールド: description, タイプ: string, 値: 説明文
- フィールド: timestamp, タイプ: timestamp, 値: 作成日時


## 管理者の追加
 + Firebaseコンソールを開く
 + Authenticationで管理者にしたいユーザーのUIDをコピー
 + Database (Firestore）で下記ドキュメントを作る

`/users/{UID}`

作成したドキュメントに下記データを追加

- フィールド: isAdmin, タイプ: boolean, 値: true
