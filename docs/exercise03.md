# Exercise3: App Service 作成

## 【目次】

![](images/ex03-0000-appsvc-create.png)

1. [App Service の作成](#app-service-の作成)
1. [App Service の動作確認](#app-service-の動作確認)


## App Service の作成

1. Azureポータル上部の検索窓で「App Service」を検索、開く

1. 一覧画面上部の [作成]-[Webアプリ] を選択

1. Webアプリの作成

    1. 基本

        * プロジェクトの詳細
            * サブスクリプション： (ハンズオン用に用意したもの)
            * リソースグループ： (環境準備で作成したもの)
        * インスタンスの詳細
            * 名前： (任意。ただしグローバルで一意になる名前)
            * 公開： `コード`
            * ランタイムスタック： `.NET 6`
            * オペレーティングシステム： `Windows`
            * 地域： `Japan East`
        * App Service プラン
            * Windows プラン： (新規作成、任意名)
            * SKU と サイズ： `Standard S1`

        ![](images/ex03-0010-appsvc-create.png)

        設定出来たら「確認および作成」を押下

    1. デプロイ

        * 継続的デプロイ: `無効化`

        ![](images/ex03-0020-appsvc-create.png)


    1. ネットワーク

        *  パブリックアクセス: `オン`
        * ネットワークインジェクション: `オフ`

        ![](images/ex03-0030-appsvc-create.png)

    1. 監視~タグ

        特に指定なし

    1. 確認および作成

        内容を確認して「作成」



## App Service の動作確認

1. 作成した App Service へ移動

1. 概要欄にある URL を確認、別ブラウザで開く

    ![](images/ex03-0110-appsvc-create.png)

1. 初期ページが開けばOK

    ![](images/ex03-0120-appsvc-create.png)



# 次の Exercise へ

* [App Service へアプリのデプロイ](exercise04.md)
