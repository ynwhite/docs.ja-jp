---
title: "NativeActivity の基本クラス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e53471a2d0245b1547ae5ee3c3a147e024aedefb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="nativeactivity-base-class"></a>NativeActivity の基本クラス
<xref:System.Activities.NativeActivity> はプロテクト コンストラクターを持つ抽象クラスです。 <xref:System.Activities.CodeActivity> と同様に、<xref:System.Activities.NativeActivity> は、<xref:System.Activities.NativeActivity.Execute%2A> メソッドを実装して、強制的な動作を記述するときに使用します。 <xref:System.Activities.CodeActivity> とは異なり、<xref:System.Activities.NativeActivity> からは、<xref:System.Activities.NativeActivityContext> メソッドに渡される <xref:System.Activities.NativeActivity.Execute%2A> オブジェクトを介して、ワークフロー ランタイムの公開されているすべての機能にアクセスできます。  
  
## <a name="using-nativeactivitycontext"></a>NativeActivityContext の使用  
 ワークフロー ランタイムの機能は、<xref:System.Activities.NativeActivity.Execute%2A> 型の `context` パラメーターを使用して、<xref:System.Activities.NativeActivityContext> メソッド内からアクセスできます。 <xref:System.Activities.NativeActivityContext> を介して、以下のような機能を使用できます。  
  
-   引数と変数を取得および設定する。  
  
-   <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A> を使用して子のアクティビティのスケジュールを設定する。  
  
-   <xref:System.Activities.NativeActivityContext.Abort%2A> を使用してアクティビティの実行を中止する。  
  
-   <xref:System.Activities.NativeActivityContext.CancelChild%2A> および <xref:System.Activities.NativeActivityContext.CancelChildren%2A> を使用して子の実行を取り消す。  
  
-   <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>、<xref:System.Activities.NativeActivityContext.RemoveBookmark%2A>、および <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A> などのメソッドを使用して、アクティビティのブックマークにアクセスする。  
  
-   <xref:System.Activities.CodeActivityContext.Track%2A> を使用したカスタムの追跡機能。  
  
-   <xref:System.Activities.CodeActivityContext.GetProperty%2A> および <xref:System.Activities.NativeActivityContext.GetValue%2A> を使用して、アクティビティの実行プロパティと値プロパティにアクセスする。  
  
-   <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> および <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A> を使用してアクティビティのアクションと機能のスケジュールを設定する。  
  
#### <a name="to-create-a-custom-activity-that-inherits-from-nativeactivity"></a>NativeActivity から継承するカスタム アクティビティを作成するには  
  
1.  [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] を開きます。  
  
2.  選択**ファイル**、**新しい**、し**プロジェクト**です。 選択**Workflow 4.0**  **Visual c#**で、**プロジェクトの種類**ウィンドウ、および選択、 **v2010**ノード。 選択**アクティビティ ライブラリ**で、**テンプレート**ウィンドウです。 新しいプロジェクトに HelloActivity という名前を付けます。  
  
3.  HelloActivity プロジェクトの Activity1.xaml を右クリックし **削除**です。  
  
4.  HelloActivity プロジェクトを右クリックし **追加**、し**クラス**です。 新しいクラスに HelloActivity.cs という名前を付けます。  
  
5.  HelloActivity.cs ファイルで、次の `using` ディレクティブを追加します。  
  
    ```csharp  
    using System.Activities;  
    using System.Activities.Statements;  
    ```  
  
6.  クラス宣言に基本クラスを追加することにより、新しいクラスで <xref:System.Activities.NativeActivity> から継承します。  
  
    ```csharp  
    class HelloActivity : NativeActivity  
    ```  
  
7.  <xref:System.Activities.NativeActivity.Execute%2A> メソッドを追加して、このクラスに機能を追加します。  
  
    ```csharp  
    protected override void Execute(NativeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
    }  
    ```  
  
8.  <xref:System.Activities.NativeActivity.CacheMetadata%2A> メソッドをオーバーライドして適切な Add メソッドを呼び出し、カスタム アクティビティの変数、引数、子およびデリゲートについてワークフロー ランタイムに通知します。 詳細については、<xref:System.Activities.NativeActivityMetadata> クラスを参照してください。  
  
9. <xref:System.Activities.NativeActivityContext> オブジェクトを使用してブックマークをスケジュールします。 ブックマークを作成、スケジュール、および再開する方法の詳細については、「<xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A>」を参照してください。  
  
    ```  
    protected override void Execute(NativeActivityContext context)  
        {  
            // Create a Bookmark and wait for it to be resumed.  
            context.CreateBookmark(BookmarkName.Get(context),   
                new BookmarkCallback(OnResumeBookmark));  
        }  
    ```
