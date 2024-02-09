---
lab:
    title: 'ラボ 3: SharePoint'
    module: 'モジュール 3: Power Automate を使用して承認フローを構築する'
---

# 実践ラボ 3 – SharePoint

このラボでは、SharePoint サイトとリストを作成します。

## 学習する内容

- SharePoint リストを作成する方法
- データのアップロード方法

## ハイレベルラボの手順

- 商談用の SharePoint リストを作成する
  
## 前提条件

- **ラボ 0: ラボ環境を検証する** を完了している必要があります。

## 詳細な手順

## 演習 1 – SharePoint リストの作成

### タスク 1.1 SharePoint サイトを作成する

1. [Power Apps メーカー ポータル](https://make.powerapps.com) で、ブラウザーウィンドウの左上にある **App launcher** を選択し、 **OneDrive** を選択します。

1. SharePoint で、 **+Create site** を選択します。

1. **Team site** を選択し、 **Standard team** テンプレートを選択し、 **Use template** を選択します。

1. **Site name** に `Power Automate` と入力し、 **Next** を選択します。

1. **Create site** を選択します。

1. **Finish** を選択します。

### タスク 1.2 SharePoint リストを作成する

1. SharePoint サイトで、 **+ New** を選択し、次に **List** を選択します。

    ![Screenshot of new SharePoint list.](../media/new-sharepoint-list.png)

1. **Blank list** を選択します。

1. **Name** に `Tasks` と入力し、 **Create** を選択します。

1. **+ Add column** を選択し、 **Multiple lines of text** を選択し、 **Next** を選択します。

1. **Create a column** ペインで、次の値を入力または選択します:

   1. 名前: `Description`
   1. データ型: **Multiple lines of text**

1. **Save** を選択します。

1. **+Add column** 、 **Text** 、 **Next** を選択します。

1. **Create a column** ペインで、次の値を入力または選択します:

   1. 名前: `Owner Name`
   1. データ型: **Single line of text**

1. **Save** を選択します。

1. **+ Add column** を選択し、 **Date and time** を選択し、 **Next** を選択します。

1. **Create a column** ペインで、次の値を入力または選択します:

   1. 名前: `Deadline`
   1. データ型: **Date and time**

1. **Save** を選択します。

1. **+ Add column** を選択し、 **Choice** を選択し、 **Next** を選択します。

1. **Create a column** ペインで、次の値を入力または選択します:

   1. 名前: `Approval Status`
   1. データ型: **Choice**
   1. 選択肢 1=`New`
   1. 選択肢 2=`Approved`
   1. 選択肢 3=`Declined`

1. **Default value** で **New** を選択します。

    ![Screenshot of new SharePoint list.](../media/add-choice-column.png)

1. **Save** を選択します。

1. SharePoint サイトの URL の最初の部分(例: `https://m365x99999999.sharepoint.com/sites/PowerAutomate/`) をコピーします。

## 演習 2 – データ SharePoint リストを追加する

### タスク 2.1 - データの追加

1. SharePoint サイトに移動し、 **Tasks** リストを選択します。

    ![Screenshot of the SharePoint Tasks list.](../media/tasks-sharepoint-list.png)

1. **+ New** を選択し、次のデータを入力して **Save** を選択します:

   1. Title=`Contact Jon`
   1. Description=`Call or email`
   1. Owner Name=`MOD Administrator`
   1. Deadline=**Yesterday**
   1. Approval Status=**Declined**

1. **+ New** を選択し、次のデータを入力して **Save** を選択します:

   1. Title=`Create Quote`
   1. Description=`No discount`
   1. Owner Name=`MOD Administrator`
   1. Deadline=**Today**
   1. Approval Status=**Approved**

1. **+ New** を選択し、次のデータを入力して  **Save** を選択します:

   1. Title=`Visit Jim`
   1. Description=`First visit`
   1. Owner Name=`MOD Administrator`
   1. Deadline=**Tomorrow**
   1. Approval Status=**New**

    ![Screenshot of the SharePoint Tasks data.](../media/tasks-data.png)
