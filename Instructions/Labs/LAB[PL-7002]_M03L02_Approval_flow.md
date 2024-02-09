---
lab:
    title: 'ラボ 4: 承認フロー'
    module: 'モジュール 3: Power Automate を使用して承認フローを構築する'
---

# 演習 4 – 承認フロー

このラボでは、承認フローを作成します。

## 学習する内容

- Power Automate 承認クラウド フローを作成する方法

## ハイレベルラボの手順

- SharePoint リストの自動クラウド フローを作成する
- 承認を作成する
- 承認結果の条件を追加する
- フローをテストする
  
## 前提条件

- **ラボ 3: SharePoint** を完了している必要があります

## 詳細な手順

## 演習 1 – 承認フローを作成する

### タスク 1.1 - トリガーの作成

1. Power Automate ポータル <https://make.powerautomate.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左型のメニューから **+ Create** タブを選択します。

1. **Automated cloud flow** を選択します。

1. **Flow name** に `Task approval` と入力します。

1. 検索に `SharePoint` と入力します。

1. **When an item is created** を選択します。

1. **Create** を選択します。

### タスク 1.2 - トリガーを構成する

1. **When an item is created** ステップを選択します。

1. **When an item is created** を選択し、 `New task` と入力します。

1. **Power Automate SharePoint site** を選択します。

1. **Tasks** リストを選択します。

    ![Screenshot of SharePoint trigger.](../media/sharepoint-trigger.png)

### タスク 1.3 - 承認アクションの追加

1. トリガーステップの下にある **+** アイコンを選択し、 **Add an action** を選択します。

1. 検索に `approval` と入力します。

    ![Screenshot of approvals search.](../media/search-approval.png)

1. **Approvals** で **Start and wait for an approval** を選択します。

1. **Create New** を選択します。

1. **Approval Type** で **Approve/Reject - First to respond** を選択します。 

1. **Start and wait for an approval** を選択し、 `Approval` と入力します。

1. **Title** フィールドを選択し、動的コンテンツアイコンを選択します。

    ![Screenshot of dynamic content for SharePoint item.](../media/sharepoint-dynamic-content.png)

1. **Title** を選択します。

1. **Assigned To** にテナントのユーザー ID を入力します。

1. **Details** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **Description** を選択します。

1. **Item Link** フィールドを選択し、動的コンテンツアイコンを選択し、 **See More** を選択します。

1. **Link to item** を選択します。

### タスク 1.4 - 条件の追加

1. 承認ステップの下にある **+** アイコンを選択し、 **Add an action** を選択します。

1. 検索に `condition` を入力します。

1. **Control** で **Condition** を選択します。

1. **Save** を選択します。

1. コマンドバーの左下にある **<-** 戻るボタンを選択します。

1. 左側の **Choose a value** フィールドを選択し、動的コンテンツアイコンを選択します。

    ![Screenshot of dynamic content for a condition.](../media/add-condition.png)

1. **Outcome** を選択します。

1. **Operator** に **is equal to** を選択します。

1. 右側の **Choose a value** フィールドを選択し、 `Approve` と入力します。

    ![Screenshot of the condition.](../media/condition.png)

### タスク 1.5 - ステータスの更新アクション

1. **True** の下の **+** アイコンを選択し、 **Add an action** を選択します。

1. 検索に `update item` と入力します。

1. **SharePoint** の下の **Update Item** を選択します。

1. **Update item** を選択し、 `Set task to approved` と入力します。

1. **Power Automate SharePoint site** を選択します。

1. **Tasks** リストを選択します。

1. **Id** フィールドを選択し、動的コンテンツを選択します。

1. **New task** から **Id** を選択します。

1. **Show all** を選択します。

1. **Title** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **New task** から **Title** を選択します。

1. **Approval Status Value** で **Approved** を選択します。

1. **False** の下の **+** アイコンを選択し、 **Add an action** を選択します。

1. 検索に `update item` と入力します。

1. **SharePoint** の下の **Update Item** を選択します。

1. **Update item 1** を選択し、 `Set task to declined` と入力します。

1. **Power Automate SharePoint site** を選択します。

1. **Tasks** リストを選択します。

1. **Id** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **New task** から **Id** を選択します。

1. **Show all** を選択します。

1. **Title** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **New task** から **Title** を選択します。

1. **Approval Status Value** で **Decline** を選択します。

1. **Save** を選択します。

1. コマンドバーの左上にある **<-** 戻るボタンを選択します。

## 演習 2 – テストの承認

### タスク 2.1 - 承認フローのトリガー

1. SharePoint サイトに移動し、 **Tasks** リストを選択します。

1. **+ New** を選択し、次のデータを入力し、 **Save**を選択します:

   1. Title=`Approval test`
   1. Description=`Test`
   1. Owner Name=`MOD Administrator`
   1. Deadline=**Today**
   1. Approval Status=**New**

### タスク 2.2 - 進行状況の承認

1. Power Automate ポータル <https://make.powerautomate.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側のメニューから **My flows** タブを選択します。

1. **Task approval** を選択します。

1. フロー実行履歴の日付と時刻を選択します。

    > ** Note: The Approvals functionality will be install in the background. This will take approximately 10 minutes.

1. 左側のメニューから **Approvals** タブを選択します。

    ![Screenshot of approvals in the portal.](../media/approvals.png)

1. **Approval test** を選択し、 **Tick** を選択し、 **Confirm** を確認します。

1. **Done** を選択します。

1. 左側のメニューから **My flows** タブを選択します。

1. **Task approval** を選択します。

1. フロー実行履歴の日付と時刻を選択します。

1. SharePoint サイトに移動し、 **Tasks** リストを選択します。

1. **Approval test** の **Approval status** が **Approved** であることを確認します。
