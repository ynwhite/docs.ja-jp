---
title: "チュートリアル : ストアド プロシージャのみの使用 (Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- vb
ms.assetid: 5a736a30-ba66-4adb-b87c-57d19476e862
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 800cc7d6a1e4aa836ebe75afcbe29a3532ee173a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="walkthrough-using-only-stored-procedures-visual-basic"></a>チュートリアル : ストアド プロシージャのみの使用 (Visual Basic)
このチュートリアルでは、ストアド プロシージャのみを使用してデータにアクセスする、基本の [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] シナリオ全体を示します。 この方法は、データ ストアへのアクセス方法を制限する目的で、データベース管理者によってよく使用されます。  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アプリケーションでストアド プロシージャを使用して、既定の動作をオーバーライドすることもできます。これは、`Create`、`Update`、および `Delete` の各プロセスで特に役立ちます。 詳細については、次を参照してください。[のカスタマイズを挿入、更新、および削除を行う](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)です。  
  
 このチュートリアルでは、Northwind サンプル データベース内のストアド プロシージャにマップされた 2 つのメソッド (CustOrdersDetail および CustOrderHist) を使用します。 SqlMetal コマンド ライン ツールを実行して [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] ファイルを生成すると、対応付けが発生します。 詳細については、このチュートリアルの「前提条件」を参照してください。  
  
 このチュートリアルは、[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]には依存しません。 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] を使用している開発者は、[!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]を使用して、ストアド プロシージャの機能を実装することもできます。 参照してください[LINQ to Visual Studio での SQL ツール](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)です。  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 このチュートリアルは、Visual Basic 開発設定を使用して記述されています。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルの前提条件は次のとおりです。  
  
-   このチュートリアルでは、専用フォルダー ("c:\linqtest3") を使用してファイルを保持します。 チュートリアルを開始する前に、このフォルダーを作成してください。  
  
-   Northwind サンプル データベース。  
  
     開発用コンピューターにこのデータベースがない場合は、Microsoft ダウンロード サイトからダウンロードします。 手順については、次を参照してください。[サンプル データベースのダウンロード](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)です。 データベースをダウンロードしたら、northwnd.mdf ファイルを c:\linqtest3 フォルダーにコピーします。  
  
-   Northwind データベースから生成された [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] コード ファイル。  
  
     このチュートリアルは、SqlMetal ツールを使用して次のコマンド ラインで作成されています。  
  
     **sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**  
  
     詳しくは、「[SqlMetal.exe (コード生成ツール)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)」をご覧ください。  
  
## <a name="overview"></a>概要  
 このチュートリアルは、主に次の 6 つの手順で構成されています。  
  
-   [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] で [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] ソリューションを設定します。  
  
-   プロジェクトに System.Data.Linq アセンブリを追加します。  
  
-   プロジェクトにデータベース コード ファイルを追加します。  
  
-   データベースへの接続を作成します。  
  
-   ユーザー インターフェイスを設定します。  
  
-   アプリケーションを実行およびテストします。  
  
## <a name="creating-a-linq-to-sql-solution"></a>LINQ to SQL ソリューションを作成する  
 最初に、[!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] プロジェクトをビルドおよび実行するために必要な参照を含む [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ソリューションを作成します。  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>LINQ to SQL ソリューションを作成するには  
  
1.  [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **ファイル** メニューのをクリックして**新しいプロジェクト**です。  
  
2.  **[新しいプロジェクト]** ダイアログ ボックスの **[プロジェクトの種類]** ペインで、 **[Visual Basic]**を展開し、 **[Windows]**をクリックします。  
  
3.  **[テンプレート]** ペインの **[Windows フォーム アプリケーション]**をクリックします。  
  
4.  **名前**ボックスに、入力**sproconlyapp」と入力**です。  
  
5.  **[OK]**をクリックします。  
  
     Windows フォーム デザイナーが開きます。  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a>LINQ to SQL アセンブリ参照を追加する  
 標準の Windows フォーム アプリケーション テンプレートには、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アセンブリは含まれていません。 次の手順に従って、アセンブリを自分で追加する必要があります。  
  
#### <a name="to-add-systemdatalinqdll"></a>System.Data.Linq.dll を追加するには  
  
1.  **ソリューション エクスプ ローラー**をクリックして**すべてのファイル**です。  
  
2.  **ソリューション エクスプ ローラー**を右クリックして**参照**、クリックして**参照の追加**です。  
  
3.  **参照の追加**ダイアログ ボックスで、をクリックして**.NET**を System.Data.Linq アセンブリをクリックし、をクリックして**OK**です。  
  
     アセンブリがプロジェクトに追加されます。  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>プロジェクトに Northwind コード ファイルを追加する  
 この手順では、事前に SqlMetal ツールを使用して、Northwind サンプル データベースからコード ファイルを生成していることが前提となります。 詳細については、このチュートリアルの「前提条件」を参照してください。  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a>プロジェクトに Northwind コード ファイルを追加するには  
  
1.  **プロジェクト** メニューのをクリックして**既存項目の追加**です。  
  
2.  **既存項目の追加**ダイアログ ボックスで c:\linqtest3\northwind.vb に移動し、をクリックして**追加**です。  
  
     プロジェクトに northwind.vb ファイルが追加されます。  
  
## <a name="creating-a-database-connection"></a>データベース接続を作成する  
 この手順では、Northwind サンプル データベースへの接続を定義します。 このチュートリアルでは、パスとして "c:\linqtest3\northwnd.mdf" を使用します。  
  
#### <a name="to-create-the-database-connection"></a>データベース接続を作成するには  
  
1.  **ソリューション エクスプ ローラー**を右クリックして**Form1.vb**、クリックして**コードの表示**です。  
  
     コード エディターに `Class Form1` が表示されます。  
  
2.  `Form1` コード ブロックに次のコードを入力します。  
  
     [!code-vb[DLinqWalk4VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#1)]  
  
## <a name="setting-up-the-user-interface"></a>ユーザー インターフェイスを設定する  
 この手順では、ユーザーがストアド プロシージャを実行してデータベース内のデータにアクセスできるように、インターフェイスを作成します。 このチュートリアルで作成するアプリケーションでは、ユーザーはアプリケーションに埋め込まれているストアド プロシージャを使用してのみ、データベース内のデータにアクセスできます。  
  
#### <a name="to-set-up-the-user-interface"></a>ユーザー インターフェイスを設定するには  
  
1.  戻り値を Windows フォーム デザイナー (**form1.vb [デザイン]**)。  
  
2.  **[表示]** メニューの **[ツールボックス]**をクリックします。  
  
     ツールボックスが表示されます。  
  
    > [!NOTE]
    >  をクリックして、**自動的に隠す**このセクションの手順を残りの実行中に、ツールボックスを開いたままにします。  
  
3.  2 つのボタン、2 つのテキスト ボックス、および 2 つのラベルをツールボックスからドラッグ**Form1**です。  
  
     図のようにコントロールを配置します。 展開**Form1**コントロールを簡単に配置できるようにします。  
  
4.  右クリック**Label1**、クリックして**プロパティ**です。  
  
5.  変更、**テキスト**プロパティから**Label1**に**Enter OrderID:**です。  
  
6.  に対して同じ方法で**Label2**、変更、**テキスト**プロパティから**Label2**に**Enter CustomerID:**です。  
  
7.  同じ方法で変更、**テキスト**プロパティを**Button1**に**Order Details**です。  
  
8.  変更、**テキスト**プロパティ**Button2**に**注文履歴**です。  
  
     すべてのテキストが表示されるように、ボタン コントロールの幅を広げます。  
  
#### <a name="to-handle-button-clicks"></a>ボタン クリックを処理するには  
  
1.  ダブルクリックして**Order Details**で**Form1**を作成する、`Button1`イベント ハンドラーと、コード エディターを開きます。  
  
2.  `Button1` のハンドラーに次のコードを入力します。  
  
     [!code-vb[DLinqWalk4VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#2)]  
  
3.  ダブルクリックして**Button2**を作成する Form1 に、`Button2`イベント ハンドラーと、コード エディターを開きます。  
  
4.  `Button2` のハンドラーに次のコードを入力します。  
  
     [!code-vb[DLinqWalk4VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#3)]  
  
## <a name="testing-the-application"></a>アプリケーションのテスト  
 次に、アプリケーションをテストします。 データ ストアに対する操作は、2 つのストアド プロシージャで実行できる処理に制限されることに注意してください。 つまり、入力した orderID に含まれている製品を返す処理と、入力した CustomerID の注文製品の履歴を返す処理のみを実行できます。  
  
#### <a name="to-test-the-application"></a>アプリケーションをテストするには  
  
1.  F5 キーを押してデバッグを開始します。  
  
     Form1 が表示されます。  
  
2.  **Enter OrderID**ボックスに、入力**10249** をクリックし、 **Order Details**です。  
  
     注文 10249 に含まれている製品がメッセージ ボックスに表示されます。  
  
     をクリックして**OK**メッセージ ボックスを閉じます。  
  
3.  **Enter CustomerID**ボックスに、入力`ALFKI`、クリックして**注文履歴**です。  
  
     メッセージ ボックスに、顧客 ALFKI の注文履歴が表示されます。  
  
     をクリックして**OK**メッセージ ボックスを閉じます。  
  
4.  **Enter OrderID**ボックスに、入力`123`、クリックして**Order Details**です。  
  
     メッセージ ボックスに "No results" が表示されます。  
  
     をクリックして**OK**メッセージ ボックスを閉じます。  
  
5.  **デバッグ** メニューのをクリックして**デバッグを停止**です。  
  
     デバッグ セッションが終了します。  
  
6.  実験が完了したらをクリックして**プロジェクトを閉じる**上、**ファイル**] メニューの [入力を求められたら、プロジェクトを保存します。  
  
## <a name="next-steps"></a>次の手順  
 いくつかの変更を加えることによって、このプロジェクトを強化できます。 たとえば、使用できるストアド プロシージャの一覧をリスト ボックスに表示し、実行するプロシージャをユーザーに選択させることができます。 レポートの出力をテキスト ファイルに送ることもできます。  
  
## <a name="see-also"></a>参照  
 [チュートリアルによる学習](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)  
 [ストアド プロシージャ](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
