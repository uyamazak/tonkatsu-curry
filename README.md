# とんかつカレーチャット設置の手引き
全部GCP Cloud Shell上で開発してます。

## インストール 
Firebaseプロジェクト作ってCloud Shellでfirebase login

git clone

## お皿（スレッド）の作り方
FireStoreで下記ドキュメントを作る

/chat/{ID}

ドキュメントに
- title:string = 皿タイトル
- description:string = 説明文
- timestamp:timestamp = 作成日時？
を追加する

## 管理者の設定
管理者にしたいユーザーのUIDをAuthenticationからコピーしてFireStoreで下記ドキュメントを作る

/users/{UID}

作成したドキュメントに
- isAdmin:boolean = true
を設定