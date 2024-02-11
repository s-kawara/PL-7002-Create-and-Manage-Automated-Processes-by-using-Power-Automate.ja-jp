---
lab:
    title: 'ラボ 6: スケジュールされたフロー'
    module: 'モジュール 5: 複数のデータ ソースにわたる Power Automate の緊密な統合'
---

# 実践ラボ 6 – スケジュールされたフロー

このラボでは、スケジュールされたフローを作成します。

## 学習する内容

- Power Automate のスケジュールされたフローを作成し、SharePoint アイテムのリストを処理する方法。

## ハイレベルラボの手順

- スケジュールされたフローを作成する
- SharePoint リストのクエリ
- データ操作を使用する
- フローをテストする
  
## 前提条件

- **ラボ 3: SharePoint**  を完了している必要があります

## 詳細な手順

## 演習 1 – スケジュールされたフローを作成する

### タスク 1.1 - トリガーの作成

1. Power Automate ポータル <https://make.powerautomate.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側のメニューから **+ Create** タブを選択します。

1. **Scheduled cloud flow** を選択します。

1. **Flow name** に `Daily New Tasks` と入力します。 

1. **Day** を選択します。

    ![Screenshot of build a scheduled flow.](../media/build-scheduled-flow.png)

1. **Create** を選択します。

### タスク 1.2 - トリガーを構成する

1. **Recurrence** ステップを選択します。

1. **Manually trigger a flow** を選択し、 `Daily` と入力します。

### タスク 1.3 - 新しいタスクのクエリ

1. トリガーステップの下にある **+** アイコンを選択し、 **Add an action** を選択します。

1. 検索に `list items` と入力します。

1. **SharePoint** で **Get items** を選択します。

1. **Get items** を選択し、 `New tasks` を入力します。

1. **Power Automate SharePoint site** を選択します。

1. **Tasks** リストを選択します。

1. **Show all** を選択します。

1. **Filter Query** フィールドを選択し、 `ApprovalStatus eq 'New'` と入力します。

    ![Screenshot of list items query.](../media/list-items.png)

### タスク 1.4 - 列の選択

1. 新しいタスクステップの下にある **+** アイコンを選択し、 **Add an action** を選択します。

1. 検索に `Select` と入力します。

1. **Runtime** に **Built-in** を選択します。

1. **Data Operations** で **Select** を選択します。

1. **From** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **New tasks** から **Body/value** を選択します。

1. **Enter key** フィールドを選択し、 `Task` を入力します。

1. **Enter value** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **New tasks** から **Title** を選択します。

1. **Enter key** フィールドを選択し、 `Description` を入力します。

1. **Enter value** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **New tasks** から **Description** を選択します。

1. **Enter key** フィールドを選択し、 `Due` と入力します。

1. **Enter value** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **New tasks** から **Deadline** を選択します。

    ![Screenshot of Select action.](../media/select-action.png)

### タスク 1.5 - テーブルの作成

1. 選択ステップの下にある **+** アイコンを選択し、 **Add an action** を選択します。

1. 検索に `create html` と入力します。

1. **Data Operations** で **Create HTML table** を選択します。

1. **Create HTML table** を選択し、`Format as HTML table` と入力します。

1. **From** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **Select** から **Output** を選択します。

    ![Screenshot of Format HTML table action.](../media/format-html-action.png)

### タスク 1.6 - 電子メールを送信する

1. HTML テーブルの作成ステップの下にある **+** アイコンを選択し、 **Add an action** を選択します。

1. 検索に `email` と入力します。

1. **Office 365 Outlook** で **Send an email (V2)** を選択します。

1. **Send an email (V2)** を選択し、 `Notify by email` と入力します。

1. **To** フィールドを選択し、 **Enter custom value** を選択します。

1. **To** にてなんとのユーザー ID を入力します。

1. **Subject** フィールドを選択し、 `Daily Tasks` と入力します。

1. **Body** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **Format as HTML table** から **Output** を選択します。

1. **Save** を選択します。

## 演習 2 – スケジュールされたフローをテストする

### タスク 2.1 - スケジュールされたフローを手動で実行する

1. **Test** を選択します。

1. **Manually** を選択します。

1. **Test** を選択します。

1. **Run flow** を選択します。

1. **Done** を選択します。

1. Power Automate ポータルで、ブラウザーウィd脳の左上にある **App launcher** を選択し、 **Outlook** を選択します。

    ![Screenshot of Format HTML table action.](../media/daily-tasks-email.png)
