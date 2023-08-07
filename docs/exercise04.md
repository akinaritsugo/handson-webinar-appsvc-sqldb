# Exercise4: App Service へアプリのデプロイ

## 【目次】

![](images/ex04-0000-deploy.png)


1. [アプリケーションのデプロイ](#アプリケーションのデプロイ)
1. [アプリケーションの動作確認](#アプリケーションの動作確認)
1. [SQL Database へデータ登録されたことを確認](#sql-database-へデータ登録されたことを確認)

## アプリケーションのクローン

(*) 開発環境上で実施

1. Visual Studio Code を開き、以下のレポジトリをクローン

    https://github.com/akinaritsugo/sample-todo-webapp-csharp.git

1. ローカルでテスト実行

    ```
    dotnet watch run
    ```



## アプリケーションのデプロイ

(*) 開発環境上で実施

1. Visual Studio Code でリポジトリのクローンを開く

1. 左メニューの「Azure」アイコンを選択

    ![](images/ex04-0101-deploy.png)

1. 「Sign in to Azure」を選択、Azureにサインイン

    ![](images/ex04-0102-deploy.png)

1. サブスクリプション、App Services を展開して 作成済 の App Service を右クリック、「Deploy to Web App」を選択

    ![](images/ex04-0103-deploy.png)

1. デプロイする対象のフォルダ選択がでるので `sample-todo-webapp-csharp` を選択

    ![](images/ex04-0104-deploy.png)

    設定ファイルの追加メッセージが表示された場合、 `Add Config` を選択

    ![](images/ex04-0105-deploy.png)
<!-- 
    設定を更新するかどうかのメッセージが表示された場合、 `No` を選択

    ![](images/ex04-0106-deploy.png)
-->



## App Service の設定

(*) Azureポータル上で実施

1. 作成済の SQL データベース を開く

1. [設定]-[接続文字列] を開く

1. 「ADO.NET」にある接続文字列（SQL認証）をメモしておく

    接続文字列中にある `{your_password}` を正しい値に修正しておく

1. 作成済の App Service を開く

1. [設定]-[構成] を開き、Connection strings に以下を追加

    | Name | Value | Type |
    |---|---|---|
    | `MSSQLDB` | (SQLデータベースで取得した接続文字列) | `SQLServer` |

1. 「Save」

1. [概要]へ戻って「再起動」


## アプリケーションの動作確認

(*) Azureポータル上で実施

1. Azure ポータルで作成済みの App Service を開き、 URL を確認

    ![](images/ex04-0201-deploy.png)

1. 別ブラウザで開いてアプリが動作していることを確認

    ![](images/ex04-0202-deploy.png)

1. 「ToDo」タブを開き、「新規タスク作成」をイラク

    ![](images/ex04-0203-deploy.png)

1. 適当な値を入力して「登録」

    * Description: (任意)
    * Created Date: (任意)

    ![](images/ex04-0204-deploy.png)

1. 新規にレコードが追加されたことを確認

    ![](images/ex04-0205-deploy.png)


## SQL Database へデータ登録されたことを確認

(*) Azureポータル上で実施

1. Azureポータルで作成済みの SQL Database を開く

1. 「クエリエディター」を開く

1. 以下のクエリを実行、登録したデータが存在することを確認

        ```
        select * from [dbo].[Tasks];
        ```

   ![](images/ex04-0206-deploy.png)


# 次の Exercise へ

* [環境削除](exercise99.md)

