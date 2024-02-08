---
lab:
    title: 'ラボ 2: データ モデル'
    module: 'モジュール 2: Microsoft Dataverse の使用を開始する'
---

# 演習 2 – データ モデル

このラボでは、Dataverse のテーブルと列を作成します。

## 学習する内容

- Microsoft Dataverse でテーブルと列を作成する方法
- ルックアップ列との関係を作成する方法

## ハイレベルラボの手順

- カスタムテーブルを作成する
- テーブルに列を追加する
- ルックアップ列を使用して との関係を作成する
  
## 前提条件

- **ラボ 0: ラボ環境の検証** を完了している必要があります

## 詳細な手順

## 演習 1 – カスタム テーブルを作成する

### タスク 1.1 - 商談テーブルの作成

1. Power Apps メーカー テーブルに <https://make.powerapps.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側のナビゲーションウィンドウで、 **Tables** を選択します。

1. **+ New table** を選択し、 **Add columns and data** を選択します。

    ![Screenshot of creating a new table in Dataverse.](../media/create-new-table-dataverse.png)

1. 新しいテーブルの横にある **pencil** アイコンを選択します。

    ![Screenshot of new table name.](../media/table-name.png)

1. **Display name** に、 `Opportunity` と入力します。

1. **Save** を選択します。

### タスク 1.2 - プライマリ列

1. **New column** の横にあるドロップダウンキャレットを選択し、 **Edit column** を選択します。

    ![Screenshot of primary column.](../media/primary-column.png)

1. **Display name** に `Opportunity Subject` と入力します。

1. **Update** を選択します。

1. **Create** を選択します。

### タスク 1.3 - 列の追加

1. **Opportunity columns and data** ペインで、 **+** を選択し、新しい列を追加します。

    ![Screenshot of data pane.](../media/data-pane.png)

1. **New column** ペインで、次の値を入力または選択します:

   1. 表示名: `Owner Name`
   1. データ型: **Single line of text**
   1. 必須: **Business required**

    ![Screenshot of new column pane.](../media/new-column-pane.png)

1. **Save** を選択します。

1. **Opportunity columns and data** ペインで、 **+** を選択して新しい列を追加します。

1. **New column** ペインで、次の値を入力まはた選択します:

   1. 表示名: `Customer`
   1. データ型: **Single line of text**
   1. 必須: **Business required**

1. **Save** を選択します。

1. **New column**  ペインで、次の値を入力まはた選択します:

   1. 表示名: `Address`
   1. データ型: **Single line of text**
   1. 必須: **Optional**

1. **Advanced option** を展開し、 **Maximum character count** に `200` と入力します。

1. **Save** を選択します。

1. **Opportunity columns and data** ペインで、 **+** を選択し、 **New column** ペインで次の値を入力または選択します:

   1. 表示名: `Estimated Close Date`
   1. データ型: **Date and time**
   1. フォーマット: **Date only**
   1. 必須: **Optional**

1. **Save** を選択します。

1. **Opportunity columns and data** ペインで、 **+** を選択し、 **New column** ペインで次の値を入力または選択します:

   1. 表示名: `Amount`
   1. データ型: **Currency**
   1. Required: **Optional**

1. **Save** を選択します。

1. I**Opportunity columns and data** ペインで、 **+** を選択し、 **New column** ペインで次の値を入力または選択します::

   1. 表示名: `Notes`
   1. データ型: **Multiple lines of text**
   1. フォーマット: **Text**
   1. 必須: **Optional**

### タスク 1.4 - 選択列の追加

1. **Opportunity columns and data** ペインで、 **+** を選択し、 **New column** ペインで次の値を入力または選択します:::

   1. 表示名: `Status`
   1. データ型: **Choice**
   1. 必須: **Optional**

1. **Sync with global choice?** で  **No** を選択します。

1. **Label** に  `New` と入力し、 **Value** に `1` を入力します。

1. **+ New choice** を選択し、 **Label** に `Open` を入力し、 **Value** に `2` を入力します。

1. **+ New choice** を選択し、 **Label** に  `Closed` と入力し、 **Value** に `3` を入力します。

1. **Default choice** で **New** を選択します。

    ![Screenshot of new choice column pane.](../media/new-local-choice.png)

1. **Save** を選択します。

## 演習 2 – 関係を作成する

### Task 2.1 - Create a lookup column

1. Power Apps メーカー ポータル <https://make.powerapps.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側のナビゲーションウィンドウで、 **Tables** を選択します。

1. **Opportunity** を選択します。

1. **Opportunity columns and data** ペインで、 **+** を選択し、 **New column** ペインで次の値を入力または選択します:

   1. 表示名: `Account`
   1. データ型: **Lookup**
   1. 必須: **Optional**
   1. 関連テーブル: **Account**

    ![Screenshot of new lookup column pane.](../media/new-lookup.png)

1. **Save** を選択します。

## 演習 3 – データ

### タスク 3.1 - 商談レコードの追加

1. Power Apps メーカー ポータル <https://make.powerapps.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側のナビゲーションウィンドウで、 **Tables** を選択します。

1. **Opportunity** を選択します。

1. **Opportunity columns and data** ペインで、 **Edit** を選択し、 **Edit in new tab** を選択します。

1. 次の値を入力または選択します:

   1. Opportunity Subject: `100 Widgets`
   1. Owner Name: `MOD Administrator`
   1. Customer: `Adventure Works`
   1. Estimated Close Date: **Pick a date in the previous month**
   1. Status: **Closed**
   1. Amount: `10,000`

1. **Inset row below** を選択し、次の値を入力または選択します:

   1. Opportunity Subject: `Key customer`
   1. Owner Name: `MOD Administrator`
   1. Customer: `Fabrikam`
   1. Estimated Close Date: **Pick a future date in the current month**
   1. Status: **New**
   1. Amount: `50,000`

1. **Inset row below**  を選択し、次の値を入力または選択します:

   1. Opportunity Subject: `New customer`
   1. Owner Name: `MOD Administrator`
   1. Customer: `Coho Winery`
   1. Estimated Close Date: **Pick a future date in the next month**
   1. Status: **New**
   1. Amount: `25,000`

1. **Inset row below**  を選択し、次の値を入力または選択します:

   1. Opportunity Subject: `Repeat customer`
   1. Owner Name: `MOD Administrator`
   1. Customer: `Fourth Coffee`
   1. Estimated Close Date: **Pick a future date in the next month**
   1. Status: **Open**
   1. Amount: `15,000`

    ![Screenshot of edit data pane.](../media/edit-data.png)

1. データ編集タブを閉じます。
