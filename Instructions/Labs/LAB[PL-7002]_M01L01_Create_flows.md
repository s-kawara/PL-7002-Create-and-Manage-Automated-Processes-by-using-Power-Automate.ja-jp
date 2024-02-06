---
lab:
    title: 'ラボ 1: クラウド フローを作成する'
    module: 'モジュール 1: Power Automate の使用を開始する'
---

# 実践ラボ 1 – クラウド フローの作成

このラボでは、クラウド フローを作成します。

## 学習する内容

- テンプレートから CoPilot を使用して Power Automate クラウド フローを作成する方法
- Power Automate クラウド フローをゼロから作成し、アクションを追加する方法

## ハイレベルラボの手順

- テンプレートからクラウド フローを作成する
- CoPilot でクラウド フローを作成する
- クラウドフローを作成する
- クラウド フロー アクティビティを監視する
  
## 前提条件

- **ラボ 0: ラボ環境を検証する**

## 詳細な手順

## 演習 1 – テンプレートからクラウド フローを作成する

### タスク 1.1 - テンプレートの選択

1. Power Automate ポータル <https://make.powerautomate.com> に移動します。

1. **Dev One** 環境を選択します。

    ![Environment selector in Power Automate.](../media/select-dev-one-environment-power-automate.png)

1. 左側のメニューから **Templates** タブを選択します。

1. **Button** タブを選択します。

1. 検索フィールドに `location` と入力します。

    ![Screenshot of flow templates.](../media/flow-templates.png)

1. **Get today's weather forecast for my current location** を選択します。

    ![Screenshot of create connections.](../media/create-connections.png)

1. **MSN Weather** の **Create** を選択します。

1. **Notifications** で **Create** を選択します。

1. **Create Flow** を選択します。

    ![Screenshot of flow details.](../media/flow-details.png)

### タスク 1.2 - フローの実行

1. **Run** を選択します。

1. プロンプトが表示されたら、 **Know your location** に対して、 **Allow** を選択します。

1. **Continue** を選択します。

1. **Run flow** を選択します。

1. **Done** を選択します。

    ![Screenshot of flow run history.](../media/run-history.png)

### タスク 1.3 - フローを確認する

1. フロー実行履歴の日付と時刻を選択します。

    ![Screenshot of flow run detail.](../media/flow-run-collapsed.png)

1. **Condition** ステップを選択して、フローステップを展開します。

    ![Screenshot of flow run steps.](../media/flow-run-steps.png)

1. 緑色のチェックマークが付いた **Get forecast for today** ステップを選択します。

    ![Screenshot of flow run step output.](../media/flow-run-step.png)

1. **Edit** を選択します。

1. **Condition** ステップを選択して、フローステップを展開します。

1. **Expand condition** を選択します。

1. **Send a push notification** ステップのいずれかを選択します。

1. **Flow checker** を選択します。エラーや警告がなようにします。

1. **Flow checker** ペインを閉じます。

### タスク 1.4 - フローをテストする

1. **Test** 、 **Automatically** 、 **With a recently used trigger** を選択し、フローを実行します。

    ![Screenshot of test flow with recently used trigger.](../media/test-flow.png)

1. **Test** を選択します。

1. コマンドバーの左上にある **<-** 戻るボタンを選択します。

## 演習 2 – CoPilot を使用してクラウド フローを作成する

### タスク 2.1 - プロンプトを入力する

1. Power Automate ポータル <https://make.powerautomate.com> に移動します。

1. **Dev One** 環境にいることを確認してください。

1. 左側のメニューから **Home** タブを選択します。

1. **Let's automate something. What should it do?** 下で、 `Every day send me an email with the daily summary from MSN Weather` と入力します。

    ![Screenshot of copilot prompt.](../media/copilot-prompt.png)

1. **Generate** を選択します。

    ![Screenshot of suggested flow.](../media/copilot-suggestion.png)

1. **Next** を選択します。

1. **Create flow** を選択します。

    ![Screenshot of flow created by Copilot.](../media/copilot-flow.png)

### タスク 2.2 - フローステップの構成

1. **Get Forecast for today** ステップを選択します。

    ![Screenshot of flow step parameters.](../media/flow-step-parameters.png)

1. **Location** に `Seattle` と入力します。

1. **X** を選択して、 **Units** をクリアし、ドロップダウンで、 **Imperial** を選択します。

1. **Save** を選択します。

1. フローをテストします。

1. コマンドバーの左上にある **<-** 戻るボタンを選択します。

## 演習 3 – クラウド フローをブランクから作成する

### タスク 3.1 - トリガーの作成

1. Power Automate ポータル <https://make.powerautomate.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側のメニューから **+ Create** タブを選択します。

1. **Automated cloud flow** を選択します。

1. **Flow name** 名に `Important email` と入力します。

1. 検索に `email` と入力します。

1. **When a new email arrives (V3)** を選択します。

    ![Screenshot of build an automated flow dialog.](../media/build-automated-flow.png)

1. **Create** を選択します。

### タスク 3.2 - トリガーを構成する

1. **When a new email arrives (V3)** ステップを選択します。

1. **Show all** を選択します。

    ![Screenshot of email trigger parameters automated flow dialog.](../media/email-trigger-parameters.png)

1. **Include attachments** で **No** を選択します。

1. **Importance** で **High** を選択します。

1. **Folder** で **Inbox** を選択します。

### タスク 3.3 - アクションの追加

1. トリガーステップの下にある **+** アイコンを選択し、 **Add an action** を選択します。

1. 検索に `notification` と入力します。

    ![Screenshot of action search.](../media/search-action.png)

1. **Microsoft Teams** で **Post a feed notification** を選択します。

1. **Sign in** を選択します。

1. テナントの認証情報を使用します。

1. **Notification Type** で **Team** を選択します。

1. **Recipient** にテナントのユーザー ID を入力します。

1. **Notification Text** フィールドを選択し、動的コンテンツアイコンを選択します。

    ![Screenshot of dynamic content.](../media/flow-dynamic-content.png)

1. **Subject** を選択します。

1. **Team** で **Contoso** を選択します。

1. **Channel** で **General** を選択します。

1. **Save** を選択します。

1. コマンドバーの左上にある **<-** 戻るボタンを選択します。

## 演習 4 – フローを監視する

### タスク 4.1 - クラウド フロー アクティビティ

1. Power Automate ポータル <https://make.powerautomate.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側メニューから **... More** を選択します。

    ![Screenshot of more options for Power Automate portal.](../media/power-automate-menu.png)

1. **Cloud flow activity** のピンアイコンを選択します。

1. 左側のメニューから **Cloud flow activity** タブを選択します。

    ![Screenshot of cloud flow activity.](../media/cloud-flow-activity.png)
