# Exercise1: SQL Database 作成

## 【目次】

![](images/ex01-0000-sqldb-create.png)

1. [SQL Database 作成](#sql-database-作成)


## SQL Database 作成

1.  Azureポータル上部の検索窓で「SQL データベース」を検索、開く

1. 一覧画面上部の「作成」を選択

1. SQL Database の作成

    1. 基本

        * サブスクリプション： (ハンズオン用に用意したもの)
        * リソースグループ： (環境準備で作成したもの)
        * データベース名： `todo`
        * サーバー： (新規作成 → 以下にある "SQL Database サーバーの作成" 参照)
        * SQLエラスティックプール： `いいえ`
        * コンピューティングとストレージ： `Basic 2GB` (以下にある "構成" 参照)
        * バックアップストレージの冗長性： `ローカル冗長`

        1. SQL Database サーバーの作成

            * サーバー名： (任意。グローバルで重複不可)
            * 場所： `Japan East`
            * 認証方法： `SQL 認証`
            * サーバー管理者ログイン、パスワード： (任意)

            ![](images/ex01-0010-sqldb-create.png)

        1. 構成

            * サービスレベル： `汎用目的 (General Purpose)`
            * コンピューティングレベル： `サーバーレス`
            * ハードウェア構成: `Standard (Gen 5)`
            * コア数：`1`
            * 最小仮想コア数: `0.5`
            * 自動停止を有効: `有効` `0日 1時間 0分`
            * データサイズ: `32GB`
            * ゾーン冗長性: `いいえ`
        
            ![](images/ex01-0020-sqldb-create.png)

        以下は "SQL Database サーバーの作成" および "構成" を含めて設定し終わった状態

        ![](images/ex01-0030-sqldb-create.png)

    1. ネットワーク

        * 接続方法： `パブリックエンドポイント`
        * ファイアウォール規則
            * Azureサービズおよびリソースにこのサーバーへのアクセスを許可する： `はい`
            * 現在のクライアントIPアドレスを追加する： `はい`
        * 接続ポリシー： `既定`
        * TLSの最小バージョン： `TLS 1.2`

        ![](images/ex01-0040-sqldb-create.png)

    1. セキュリティ

        特に設定なし（デフォルトのまま）

    1. 追加設定

        * 既存データを使用: `なし`
        * 照合順序: `Latin1_General_100_CI_AI_SC_UTF8`
        * メンテナンス期間: `システムの規定値`

        ![](images/ex01-0050-sqldb-create.png)


    1. タグ

        特に設定なし（デフォルトのまま）

    1. 確認および作成

        内容を確認して「作成」



## SQL Database の動作確認

1. 作成した SQL データベース へ移動

1. 「クエリエディター」を開く

    ![](images/ex01-0110-sqldb-create.png)

1. 作成した SQL認証 の ユーザーID/パスワード を入力して「OK」

    ![](images/ex01-0120-sqldb-create.png)

1. 入ることができればOK

    ![](images/ex01-0130-sqldb-create.png)



# 次の Exercise へ

* [SQL Database スキーマ作成](exercise02.md)
