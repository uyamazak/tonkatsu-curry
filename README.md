# とんかつカレーチャット設置の手引き

## お皿（スレッド）の作り方
FireStoreで下記ドキュメントを作る

/chat/{ID}

ドキュメントに
title:string
timestamp:timestamp
を追加する

## 管理者の設定
管理者にしたいユーザーのUIDをAuthenticationからコピーしてFireStoreで下記ドキュメントを作る

/users/{UID}

作成したドキュメントにisAdmin:booleanでtrueを設定