---
lab:
    title: 'ラボ 7: トリガー フィルター'
    module: 'モジュール 5: 複数のデータ ソースにわたる Power Automate の緊密な統合'
---

# 演習 7 – トリガーフィルター

このラボでは、更新トリガーでフィルターをかけます。

## 学習する内容

- トリガーをフィルタリングする方法

## ハイレベルラボの手順

- 自動化されたフローを作成する
- 列フィルタを追加する
- クエリフィルターを追加

## 前提条件

- **ラボ 2: データ モデル** を完了している必要があります

## 詳細な手順

## 演習 1 - スキーマ名

### タスク 1.1 - 列スキーマ名

1. Power Apps メーカー ポータル <https://make.powerapps.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側のナビゲーションウィンドウで、 **Tables** を選択します。

1. **Opportunity** を選択します。

1. **Schema** で **Columns** を選択します。

1. **Status** 列を選択します。

1. **Advanced options** を展開します。

    ![Screenshot of column schema name.](../media/column-schema-name.png)

1. フローで使用するために **logical name** をコピーします。

   > ** Note: The prefix for your status column will be different.

## 演習 2 – 自動フローの作成

### タスク 2.1 - トリガーの作成

1. Power Automate ポータル <https://make.powerautomate.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側のメニューから **+ Create** タブを選択します。

1. **Automated cloud flow** を選択します。

1. **Flow name** 名に `Opportunity Closed` と入力します。

1. 検索に `Dataverse` と入力します。

1. **When a row is added, modified, or deleted** を選択します。

1. **Create** を選択します。

### タスク 2.2 - トリガーを構成する

1. **When a row is added, modified, or deleted** ステップを選択します。

1. **When a row is added, modified, or deleted** を選択し、 `Opportunity changed` と入力します。

1. **Change Type** で **Modified** を選択します。

1. **Table Name** として **Opportunities** を選択します。

1. **Scope** として **Organization** を選択します。

    ![Screenshot of update row trigger.](../media/update-trigger.png)

### タスク 2.3 - 電子メールを送信する

1. トリガーステップの下にある **+** アイコンを選択し、 **Add an action** を選択します。

1. 検索に `email` と入力します。

1. **Office 365 Outlook** で **Send an email (V2)** を選択します。

1. **Send an email (V2)** を選択し、 `Notify by email` と入力します。

1. **To** フィールドを選択し、 **Enter custom value** を選択します。

1. **To** にテナントのユーザー ID を入力します。

1. **Subject** フィールドを選択し、 `Opportunity closed` と入力します。

1. **Body** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **Opportunity changed** から **Opportunity Subject** を選択します。

1. **Body** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **Opportunity changed** から **Status** を選択します。

### タスク 2.4 - 列フィルター

1. **Opportunity changed** ステップを選択します。

1. **Show all** を選択します。

1. **Select Columns** フィールドを選択し、 `cr977_status` と入力します。

   > ** Note: The prefix for your status column will be different.

### タスク 2.5 - 行フィルター

1. **Opportunity changed** ステップを選択します。

1. **Show all** を選択します。

1. **Filter Rows** フィールドを選択し、 `cr977_status eq 3` と入力します。

    ![Screenshot of trigger filter.](../media/trigger-filter.png)

    > ** 注: ステータス列の接頭辞は異なります。

1. **Save** を選択します。

1. コマンドバーの左上にある **<-** 戻るボタンを選択します。
