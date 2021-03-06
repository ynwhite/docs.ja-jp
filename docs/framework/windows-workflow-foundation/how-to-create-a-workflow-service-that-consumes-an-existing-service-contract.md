---
title: "既存のサービス コントラクトを使用するワークフロー サービスを作成する方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a754875dc3f7968086f4f92044205b8ebceb01e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a>既存のサービス コントラクトを使用するワークフロー サービスを作成する方法
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] では、コントラクト優先ワークフローの開発という形で、Web サービスとワークフローの統合が向上しています。 コントラクト優先ワークフローの開発ツールでは、コードのコントラクトを先に設計できます。 その後、ツールボックス内に、コントラクト内の操作用のアクティビティ テンプレートが自動的に生成されます。  
  
> [!NOTE]
>  このトピックでは、コントラクト優先ワークフロー サービスを作成する手順について説明します。 [!INCLUDE[crabout](../../../includes/crabout-md.md)]コントラクト優先ワークフロー サービス開発を参照してください[コントラクト最初のワークフロー サービス開発](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md)です。  
  
### <a name="creating-the-workflow-project"></a>ワークフロー プロジェクトの作成  
  
1.  [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] で、**[ファイル]**、**[新しいプロジェクト]** を順に選択します。 選択、 **WCF**ノードの下、 **c#**内のノード、**テンプレート**ツリー、および選択、 **WCF ワークフロー サービス アプリケーション**テンプレート。  
  
2.  新しいプロジェクトの名前`ContractFirst` をクリック**Ok**です。  
  
### <a name="creating-the-service-contract"></a>サービス コントラクトの作成  
  
1.  プロジェクトを右クリックして**ソリューション エクスプ ローラー**選択**追加**、**新しい項目の追加**. 選択、**コード**、左側のノードと**クラス**右側のテンプレートです。 新しいクラスの名前を`IBookService` をクリック**Ok**です。  
  
2.  表示されるコード ウィンドウの上部で、`System.Servicemodel` に対する Using ステートメントを追加します。  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3.  サンプルのクラス定義を次のインターフェイス定義に変更します。  
  
    ```  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4.  キーを押してプロジェクトをビルド**Ctrl + Shift + B**です。  
  
### <a name="importing-the-service-contract"></a>サービス コントラクトのインポート  
  
1.  プロジェクトを右クリックして**ソリューション エクスプ ローラー**選択**サービス コントラクトのインポート**です。 **\<現在のプロジェクト >**すべてのサブノードを開き、選択**IBookService**です。 **[OK]**をクリックします。  
  
2.  ダイアログが表示され、操作が正常に完了したことと、プロジェクトをビルドすると、生成されたアクティビティがツールボックスに表示されることが示されます。 **[OK]**をクリックします。  
  
3.  キーを押してプロジェクトをビルド**Ctrl + Shift + B**インポートしたアクティビティがツールボックスに表示されるように、します。  
  
4.  **ソリューション エクスプ ローラー**Service1.xamlx を開きます。 ワークフロー サービスがデザイナーに表示されます。  
  
5.  選択、**シーケンス**アクティビティ。 [プロパティ] ウィンドウ、**しています.** ボタンをクリックして、 **ImplementedContract**プロパティです。 **型コレクション エディター**ウィンドウが表示されたら、をクリックして、**型**ドロップダウン リストを選択し、**型を参照しています.** エントリです。 **型の参照と選択 .Net**ダイアログで、 **\<現在のプロジェクト >**すべてのサブノードを開き、選択**IBookService**です。 **[OK]**をクリックします。 **型コレクション エディター**ダイアログ ボックスで、をクリックして**OK**です。  
  
6.  選択し、削除、 **ReceiveRequest**と**SendResponse**アクティビティ。  
  
7.  ツールボックスからドラッグして、 **Buy_ReceiveAndSendReply**と**Checkout_Receive**上にアクティビティ、**シーケンシャル サービス**アクティビティ。
