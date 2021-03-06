---
title: "トランザクションの基礎"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 353f4ee2-e6bf-4b1c-b1c8-385fc8a486c0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fa26531b1d2573b4bef49ec93f4205716227e25b
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2018
---
# <a name="transaction-fundamentals"></a>トランザクションの基礎
トランザクションとは、複数のタスクを互いに結合したものです。 たとえば、あるアプリケーションが 2 つのタスクを実行するものとします。 まず、このアプリケーションはデータベースに新しいテーブルを作成します。 次に、データを収集、フォーマットし、新しく作成したテーブルに挿入する特定のオブジェクトを呼び出します。 この 2 つのタスクは、単に関連しているだけでなく、相互に依存しており、たとえば、新しいテーブルにデータを格納できなければ新しいテーブルを作成しないようにできます。 単一のトランザクションのスコープ内でこの 2 つのタスクを実行すると、両タスク間の結合が行われます。 第 2 のタスクが失敗すると、新しいテーブルの作成以前の時点まで第 1 のタスクがロールバックされます。  
  
 動作を予測できるようにするため、すべてのトランザクションは基本 ACID プロパティ (atomic、consistent、isolated、および durable) を持つ必要があります。 これらのプロパティは、ミッション クリティカルなトランザクションの役割を悉無律型の命題として規定します。 ACID の詳細についてを参照してください[ACID プロパティ](http://go.microsoft.com/fwlink/?LinkId=98791)です。 要約すると、ACID を使用すれば、一連の関連タスクを 1 つの単位として成功または失敗させることができます。 トランザクション処理の用語でいえば、トランザクションはコミットされるか中止されるかのいずれかである、ということになります。 トランザクションをコミットするためには、すべての参加要素が、データに対する変更は永続化されるということを保証する必要があります。 システム クラッシュその他の予期しない出来事が発生した場合でも、変更は保持されます。 この保証を履行しない参加要素が 1 つでもあると、トランザクション全体が失敗します。 そのトランザクションのスコープ内でのデータに対するすべての変更が、特定の時点までロールバックされます。  
  
 トランザクションは、データベースやメッセージ キューなどの単一のデータ リソースに収容することができます。 このシナリオでは、ローカル トランザクションは、パフォーマンスを向上させる <xref:System.Transactions> が提供するトランザクション マネージャーによって管理されます。 これらのトランザクションは、データ リソースによって制御されるため、効率的で管理しやすくなっています。  
  
 さらに、トランザクションは複数のデータ リソースにまたがることもできます。 分散トランザクションにより、さまざまなシステムで発生する複数の異なる操作を、単一の成功または失敗操作に統合することができます。 このシナリオでは、トランザクションは、各システムに常駐する Microsoft 分散トランザクション コーディネーター (MSDTC) によって調整されます。  
  
 <xref:System.Transactions> の提供するクラスを使用してトランザクション アプリケーションを開発する際は、必要なトランザクションの種類や関連するトランザクション マネージャーを気にする必要はありません。 <xref:System.Transactions> インフラストラクチャが自動的にこれらを管理します。  
  
 トランザクションの作成時に、トランザクションに適用する分離レベルを指定できます。 によって定義された、分離レベルで、<xref:System.Transactions.IsolationLevel>列挙型、他のトランザクションがデータに影響は、トランザクション アクセスのレベルを決定します。  
  
 ADO.NET を使用してトランザクションを作成する<xref:System.EnterpriseServices>、または、トランザクション プログラミング モデルによって提供される、<xref:System.Transactions>名前空間。 [System.Transactions によって提供される機能](../../../../docs/framework/data/transactions/features-provided-by-system-transactions.md)を使用して、トランザクション アプリケーションの記述に使用できる機能について説明、<xref:System.Transactions>名前空間。  
  
## <a name="see-also"></a>参照  
 [System.Transactions により提供される機能](../../../../docs/framework/data/transactions/features-provided-by-system-transactions.md)
