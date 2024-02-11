---
lab:
    title: 'ラボ 5: ボタン フロー'
    module: 'モジュール 4: ユーザー情報を管理するためのフローを構築する'
---

# 演習 5 – ボタン フロー

このラボでは、ボタン フローを作成します。

## 学習する内容

- Power Automate インスタント ボタン フローを作成する方法

## ハイレベルラボの手順

- ボタンフローを作成する
- トリガートークンを使用する
- ユーザー入力を追加する
- フローをテストする
  
## 前提条件

- **ラボ 2: データ モデル** を完了している必要があります

## 詳細な手順

## 演習 1 – ボタン フローの作成

### タスク 1.1 - トリガーの作成

1. Power Automate ポータル <https://make.powerautomate.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側のメニューから **+ Create** タブを選択します。

1. **Instant cloud flow** を選択します。

1. **Flow name** に `Create opportunity` と入力します。 

1. **Manually trigger a flow** を選択します。

1. **Create** を選択します。

### タスク 1.2 - ユーザー入力の追加

1. **Manually trigger a flow** ステップを選択します。

1. **Manually trigger a flow** を選択し、 `Button clicked` と入力します。

1. **Add an input** を選択します。

1. **Text** を選択します。

1. **Input** に `Customer Name` を入力します。

1. **Please enter your input** に `Please enter the customer name` と入力します。

1. **Add an input** を選択します。

1. **Text** を選択します。

1. **Input** に `Comments` を入力します。

1. **Please enter your input** に `Any comments` と入力します。

1. **Add an input** を選択します。

1. **Number** を選択します。

1. **Input** に `Potential Sale` と入力します。

    ![Screenshot of user input.](../media/user-input.png)

### タスク 1.3 - 商談作成アクションの追加

1. トリガーステップの下にある **+** アイコンを選択し、 **Add an action** を選択します。

1. 検索に `add row` と入力します。

1. **Dataverse** の下の **Add a new row** を選択します。

1. **Sign In** を選択します。

1. テナントの認証情報を使用します。

1. **Add a new row** を選択し、 `New opportunity` と入力します。

1. **Table Name** として **Opportunities** を選択します。

1. **Customer** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **Customer Name** を選択します。

1. **Opportunity Subject** フィールドを選択し、 `New opportunity` と入力します。

1. **Owner Name** フィールドを選択し、 `MOD Administrator` と入力します。

1. **Show all** を選択します。

1. **Address** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **Full address** を選択します。

1. **Amount** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **Potential Sale** を選択します。

1. **Notes** フィールドを選択し、動的コンテンツアイコンを選択します。

1. **Comments** を選択します。

1. **Estimated Close Date** フィールドを選択し、式アイコンを選択します。

1. 式 `addDays(utcNow(),30)` を入力kし、 **Add** を選択します。

    ![Screenshot of new opportunity action.](../media/new-opportunity-action.png)

1. **Save** を選択します。

## 演習 2 – ボタン フローをテストする

### タスク 2.1 - 実行ボタンのフロー

1. **Test** を選択します。

1. **Manually** を選択します。

1. **Test** を選択します。

    ![Screenshot of testing button flow.](../media/user-input-test.png)

1. 次の詳細を入力します:

   1. Customer Name=`Button test`
   1. Comments=`This is a test`
   1. Potential Sale=`9999`

1. **Run flow** を選択します。

1. **Done** を選択します。

1. コマンドバーの左上にある **<-** 戻るボタンを選択します。

### タスク 2.2 - 作成された商談レコードの確認

1. Power Autoamte メーカーポータル <https://make.powerapps.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側のナビゲーションウィンドウで、 **Tables** を選択します。

1. **Opportunity** を選択します。
