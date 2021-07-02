①課題内容（どんな作品か）
 -必要あれば操作方法等こちらに記載

 動作に必要なDB/table
 DB名:gs_db
 table:
    gs_collection_table 
        id int(12) AUTO_INCRIMENT PLYMARY
        character_id int(12)
        character_name varchar(128)
        character_img varchar(128)
        datetime datetime

    gs_gachagacha_table 
        id int(12) AUTO_INCRIMENT PLYMARY
        character_id int(12)
        character_name varchar(128)
        character_img varchar(128)
        datetime datetime

    gs_user_table
        id int(12) AUTO_INCRIMENT PLYMARY
        user_name varchar(128)
        user_id varchar(64)
        user_pw varchar(64)           life_flag int(1)
        datetime datetime

＊gs_gachagacha_tableにgs_gachagacha_table.sqlをインポートしてgachagachaの中身を作成する

よくあるガチャ機能のあるWEBアプリを再現してみた。
構成要素
・スタート画面
・ログイン画面　新規ユーザー追加画面
・ホーム画面
・ガチャの種類選択画面
・ガチャ結果画面
・コレクション画面
・設定画面
・ユーザー情報更新画面
・ログアウトボタン

②工夫した点・こだわった点
・DBでログインIDとPWを確認してその後session_idを利用してログイン認証を行っている。
・redirect.phpを作成してページのリダイレクト用のPHPを作成してみた。
・授業の先取りとしてSQLのUPDATEでユーザー情報の更新とDELETEでコレクションの削除を行えるようにした。
・DBに画像のパスを登録してローカルの画像を表示する機能を付けた。
・ログアウト機能を付けてsession_idとcookieを破棄している
*前回からの変更点としてtitleとloginの画像を全画面表示で行うようにcssを追加した。
collectionから削除を行う際にポップアップで削除の確認を表示して確認を求める機能を追加した。

③質問・疑問（あれば）
collection.phpの20行目から33行目はもう少し簡単に書くことができるのでしょうか？

④その他（感想、シェアしたいことなんでも）
「""」と「''」が一行の中に複数回登場するとどの組み合わせかわからなくなる。