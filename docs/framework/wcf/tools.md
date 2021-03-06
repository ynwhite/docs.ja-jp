---
title: "Windows Communication Foundation ツール"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, tools
- Windows Communication Foundation, tools
ms.assetid: 399a47b4-bfea-434b-8e83-f76b5063d79d
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e28158076fcedf8c7d14d598b1c2ba0a25ff1f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="windows-communication-foundation-tools"></a>Windows Communication Foundation ツール
Microsoft [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] ツールは、[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] アプリケーションの作成、展開、および管理を簡単に行うために設計されています。 このセクションには、これらのツールに関する詳細な情報があります。 ツールはサポートされていません。  
  
 すべてのツールは、コマンド ラインから実行できます。  
  
 次の表は、ツールの一覧と簡単な説明を示します。  
  
|ツール|説明|  
|----------|-----------------|  
|[ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)|メタデータ ドキュメントからサービス モデル コードを生成し、サービス モデル コードからメタデータ ドキュメントを生成します。|  
|[秘密キー検索ツール (FindPrivateKey.exe)](../../../docs/framework/wcf/find-private-key-tool-findprivatekey-exe.md)|指定されたストアから秘密キーを取得します。|  
|[ServiceModel 登録ツール (ServiceModelReg.exe)](../../../docs/framework/wcf/servicemodelreg-exe.md)|単一コンピューター上で ServiceModel の登録と登録解除を管理します。|  
|[COM+ サービス モデル構成ツール (ComSvcConfig.exe)](../../../docs/framework/wcf/com-service-model-configuration-tool-comsvcconfig-exe.md)|COM+ インターフェイスを Web サービスとして公開されるように構成します。|  
|[構成エディター ツール (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)|WCF サービスの構成設定を作成および変更します。|  
|[サービス トレース ビューアー ツール (SvcTraceViewer.exe)](../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)|WCF サービスの問題を診断、修復、および検証できるように、トレース メッセージの表示、グループ化、およびフィルター処理を容易にします。|  
|[WS-AtomicTransaction 構成ユーティリティ (wsatConfig.exe)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)|コマンド ライン ツールを使用して、基本的な WS-AtomicTransaction サポート設定を構成します。|  
|[WS-AtomicTransaction 構成 MMC スナップイン](../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md)|MMC スナップインを使用して、基本的な WS-AtomicTransaction サポート設定を構成します。|  
|[ワークフロー サービス登録ツール (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md)|Windows ワークフロー サービスを登録します。|  
|[WCF サービス ホスト (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)|ライブラリ (*.dll) ファイルに含まれている [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] サービスをホストします。|  
|[WCF のテスト用クライアント (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)|任意の型のパラメーターを入力し、その入力をサービスに送信して、サービスから返される応答を表示するために使用される GUI ツールです。|  
|[コントラクト優先ツール](../../../docs/framework/wcf/contract-first-tool.md)|XSD データ コントラクトからコード クラスを作成する Visual Studio のビルド タスク。|  
  
 ServiceModelReg.exe、WsatConfig.exe、および ComSvcConfig.exe を除き、これらすべてのツールは Windows SDK に付属しており、C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin フォルダーにあります。  上記の 3 つのツールは、C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation にあります。
