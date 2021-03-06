---
title: "クライアントの拡張"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- proxy extensions [WCF]
ms.assetid: 1328c61c-06e5-455f-9ebd-ceefb59d3867
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2444488418b7647111cf4b89db0c41a8e66470d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="extending-clients"></a>クライアントの拡張
呼び出し側のアプリケーションでは、サービス モデル レイヤーが、アプリケーション コードでのメソッド呼び出しを送信メッセージに変換し、それらを基になるチャネルにプッシュし、結果をアプリケーション コードで戻り値と出力パラメーターに変換して、変換結果を呼び出し側に返します。 サービス モデル拡張は、クライアントやディスパッチャーの機能、カスタム動作、メッセージとパラメーターの途中受信、およびその他の拡張機能に関連する実行や通信の動作と機能を変更または実装します。  
  
 ここでは、<xref:System.ServiceModel.Dispatcher.ClientRuntime> クライアント アプリケーションで <xref:System.ServiceModel.Dispatcher.ClientOperation> クラスと [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] クラスを使用して、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアントの既定の実行動作を変更したり、メッセージ、パラメーター、または戻り値を、チャネル レイヤーから送信または取得する前後に途中受信したり、変更したりする方法について説明します。 サービス ランタイムの拡張の詳細については、次を参照してください。[ディスパッチャーの拡張](../../../../docs/framework/wcf/extending/extending-dispatchers.md)です。 動作を変更して、クライアント ランタイムにカスタマイズ オブジェクトを挿入に関する詳細については、次を参照してください。[を構成すると、ランタイムのビヘイビアーの使用を拡張する](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)です。  
  
## <a name="clients"></a>クライアント  
 クライアントでは、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント オブジェクトまたはクライアント チャネルが、メソッド呼び出しを送信メッセージに、受信メッセージを操作結果に変換し、この操作結果を呼び出し側のアプリケーションに返します  (クライアントの種類の詳細については、次を参照してください[WCF クライアント アーキテクチャ](../../../../docs/framework/wcf/feature-details/client-architecture.md)。)。  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアントの種類には、このようなエンドポイント レベルと操作レベルの機能を処理するランタイム型があります。 アプリケーションが操作を呼び出すと、<xref:System.ServiceModel.Dispatcher.ClientOperation> が送信オブジェクトをメッセージに変換し、インターセプターを処理し、送信呼び出しがターゲット コントラクトに適合することを確認してから、送信メッセージを <xref:System.ServiceModel.Dispatcher.ClientRuntime> に渡します。このクラスは、送信チャネル (双方向サービスの場合には、さらに受信チャネル) の作成と管理、追加の送信メッセージ処理 (ヘッダーの変更など)、メッセージ インターセプターの両方向での処理、および適切なクライアント側 <xref:System.ServiceModel.Dispatcher.DispatchRuntime> オブジェクトへの受信双方向呼び出しのルーティングを実行します。 <xref:System.ServiceModel.Dispatcher.ClientOperation> と <xref:System.ServiceModel.Dispatcher.ClientRuntime> は、共にメッセージ (エラーを含む) がクライアントに返されるときに同様のサービスを提供します。  
  
 これら 2 つのランタイム クラスは、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] のクライアント オブジェクトとチャネルの処理をカスタマイズするための主要な拡張機能です。 <xref:System.ServiceModel.Dispatcher.ClientRuntime> クラスは、ユーザーが、コントラクト内のすべてのメッセージについてクライアント実行を途中受信して拡張できるようにします。 <xref:System.ServiceModel.Dispatcher.ClientOperation> クラスは、ユーザーが、特定の操作内のすべてのメッセージについてクライアント実行を途中受信して拡張できるようにします。  
  
 プロパティの変更やカスタマイズの挿入は、コントラクト、エンドポイント、および操作の各動作を使用して行います。 これらの種類の動作を使用して、クライアント ランタイムのカスタマイズを実行する方法の詳細については、次を参照してください。[を構成すると、ランタイムのビヘイビアーの使用を拡張する](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)です。  
  
## <a name="scenarios"></a>シナリオ  
 クライアント システムを拡張する理由としては、次のようなさまざまなものがあります。  
  
-   カスタム メッセージの検証。 特定のスキーマに対してメッセージが有効になるようにする必要が生じる場合があります。 これは、<xref:System.ServiceModel.Dispatcher.IClientMessageInspector> インターフェイスを実装し、この実装を <xref:System.ServiceModel.Dispatcher.DispatchRuntime.MessageInspectors%2A> プロパティに割り当てることで可能になります。 例については、次を参照してください。[する方法: を検査または変更がクライアントにメッセージ](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md)と[する方法: を検査または変更がクライアントにメッセージ](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md)です。  
  
-   カスタム メッセージのログ記録。 エンドポイントを通過するアプリケーション メッセージの一部を検査して記録する必要が生じる場合があります。 これはメッセージ インターセプター インターフェイスで実行可能です。  
  
-   カスタム メッセージの変換。 アプリケーション コードを変更するのではなく、ランタイムのメッセージに特定の変換を適用する必要が生じる場合があります (バージョン管理の場合など)。 これもまた、メッセージ インターセプター インターフェイスで実行可能です。  
  
-   カスタム データ モデル。 既定で [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] でサポートされているオブジェクト (つまり、<xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> オブジェクト、<xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> オブジェクト、および <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType> オブジェクト) 以外のデータ モデルやシリアル化モデルをユーザーが必要とする場合があります。 これは、メッセージ フォーマッタ インターフェイスを実装することで対応できます。 詳細については、<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType> および <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A?displayProperty=nameWithType> プロパティのトピックを参照してください。  
  
-   カスタム パラメーターの検証。 XML ではなく、型指定されたパラメーターが有効になるようにする必要が生じる場合があります。 これは、パラメーター インスペクター インターフェイスを使用して実行できます。 例については、次を参照してください。[する方法: 検査パラメーターまたは変更](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-parameters.md)または[クライアント検証](../../../../docs/framework/wcf/samples/client-validation.md)です。  
  
### <a name="using-the-clientruntime-class"></a>ClientRuntime クラスの使用  
 <xref:System.ServiceModel.Dispatcher.ClientRuntime> クラスは、メッセージを途中受信してクライアントの動作を拡張する拡張オブジェクトを追加できる拡張ポイントです。 途中受信オブジェクトには、特定のコントラクト内のすべてのメッセージを処理する、特定の操作用のメッセージだけを処理する、カスタムのチャネル初期化を実行する、その他のカスタム クライアント アプリケーションの動作を実行する、などの機能があります。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackDispatchRuntime%2A> プロパティは、サービス側開始のコールバック クライアント用のディスパッチ ランタイム オブジェクトを返します。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.OperationSelector%2A> プロパティは、カスタムの操作セレクター オブジェクトを受け取ります。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ChannelInitializers%2A> プロパティを使用すると、クライアント チャネルを検査または変更できるチャネル初期化子を追加できます。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.Operations%2A> プロパティは、<xref:System.ServiceModel.Dispatcher.ClientOperation> オブジェクトのコレクションを取得します。このコレクションにカスタムのメッセージ インターセプターを追加すれば、その操作のメッセージに固有の機能を提供できます。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ManualAddressing%2A> プロパティをアプリケーションで使用すると、自動アドレス指定ヘッダーをオフにしてアドレス指定を直接制御できます。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.Via%2A> プロパティは、トランスポート レベルでメッセージの送信先の値を設定して、メッセージの中継者やその他のシナリオをサポートします。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> プロパティは、<xref:System.ServiceModel.Dispatcher.IClientMessageInspector> オブジェクトのコレクションを取得します。このコレクションには、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 経由のすべてのメッセージに対応するカスタム メッセージ インターセプターを追加できます。  
  
 また、コントラクト情報を取得するその他のプロパティも多数用意されています。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractName%2A>  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractNamespace%2A>  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractClientType%2A>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアントが双方向 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアントの場合は、次のプロパティもコールバック [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント情報を取得します。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackClientType%2A>  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackDispatchRuntime%2A>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] のクライアント実行を [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント全体で拡張するには、<xref:System.ServiceModel.Dispatcher.ClientRuntime> クラスに用意されているプロパティを調べ、目的の機能を作成するために、プロパティを変更するか、またはインターフェイスを実装してプロパティに追加するかを確認します。 作成する特定の拡張を選択した後は、適切な <xref:System.ServiceModel.Dispatcher.ClientRuntime> プロパティにその拡張を挿入します。挿入するには、実行時に <xref:System.ServiceModel.Dispatcher.ClientRuntime> クラスにアクセスを提供するクライアント動作を実装します。  
  
 カスタム拡張オブジェクトは、操作動作 (<xref:System.ServiceModel.Description.IOperationBehavior> を実装するオブジェクト)、コントラクト動作 (<xref:System.ServiceModel.Description.IContractBehavior> を実装するオブジェクト)、またはエンドポイント動作 (<xref:System.ServiceModel.Description.IEndpointBehavior> を実装するオブジェクト) を使用して、コレクションに挿入できます。 インストール動作オブジェクトは、プログラムで直接に、または宣言を介して (カスタム属性を実装して)、さらにアプリケーション構成ファイルを使用して動作を挿入できるようにするカスタム <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> オブジェクトを実装することにより、適切な動作コレクションに追加されます。 詳細については、「[を構成して、ランタイムのビヘイビアーの使用を拡張する](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)です。  
  
 間での傍受を示す例について、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]クライアントを参照してください[する方法: 変更がクライアントにメッセージを検査または](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md)です。  
  
### <a name="using-the-clientoperation-class"></a>ClientOperation クラスの使用  
 <xref:System.ServiceModel.Dispatcher.ClientOperation> クラスは、1 つのサービス操作のスコープ内だけに適用されるカスタムの拡張を実現するために、クライアント ランタイムに対して変更または挿入を行う場所です。 (コントラクト中のすべてのメッセージに対するクライアントのランタイム動作を変更するには、<xref:System.ServiceModel.Dispatcher.ClientRuntime> クラスを使用します。)  
  
 <xref:System.ServiceModel.Dispatcher.ClientRuntime.Operations%2A> プロパティを使用して、特定のサービス操作を表す <xref:System.ServiceModel.Dispatcher.ClientOperation> オブジェクトを検索します。 次の各プロパティを使用すると、カスタム オブジェクトを [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント システムに挿入できます。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A> プロパティは、特定の操作用に <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> のカスタムの実装を挿入したり、現在のフォーマッタを変更するために使用します。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A> プロパティは、<xref:System.ServiceModel.Dispatcher.IParameterInspector> のカスタムの実装を挿入したり、現在の実装を変更するために使用します。  
  
 次の各プロパティを使用すると、フォーマッタおよびカスタムのパラメーター インスペクターとやり取りしてシステムを変更できます。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientOperation.SerializeRequest%2A> プロパティは、送信メッセージのシリアル化を制御するために使用します。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientOperation.DeserializeReply%2A> プロパティは、受信メッセージの逆シリアル化を制御するために使用します。  
  
-   要求メッセージの WS-Addressing 操作を制御する場合に <xref:System.ServiceModel.Dispatcher.ClientOperation.Action%2A> プロパティを使用します。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientOperation.BeginMethod%2A> プロパティと <xref:System.ServiceModel.Dispatcher.ClientOperation.EndMethod%2A> プロパティは、非同期操作に関連付けられる [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント メソッドを指定するために使用します。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientOperation.FaultContractInfos%2A> プロパティは、SOAP エラーの際に詳細な型として表示できる型を含むコレクションを取得するために使用します。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientOperation.IsInitiating%2A> プロパティおよび <xref:System.ServiceModel.Dispatcher.ClientOperation.IsTerminating%2A> プロパティは、操作が呼び出されたとき、それぞれセッションを起動するか終了するかを制御するために使用します。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientOperation.IsOneWay%2A> プロパティは、操作が一方向の操作であるかどうかを制御するために使用します。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientOperation.Parent%2A> プロパティは、<xref:System.ServiceModel.Dispatcher.ClientRuntime> の親オブジェクトを取得するために使用します。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientOperation.Name%2A> プロパティは、操作の名前を取得するために使用します。  
  
-   <xref:System.ServiceModel.Dispatcher.ClientOperation.SyncMethod%2A> プロパティは、操作にマップされるメソッドを制御するために使用します。  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] のクライアント実行を 1 つのサービス操作でのみ拡張するには、<xref:System.ServiceModel.Dispatcher.ClientOperation> クラスに用意されているプロパティを調べ、目的の機能を作成するために、プロパティを変更するか、またはインターフェイスを実装してプロパティに追加するかを確認します。 作成する特定の拡張を選択した後は、適切な <xref:System.ServiceModel.Dispatcher.ClientOperation> プロパティにその拡張を挿入します。挿入するには、実行時に <xref:System.ServiceModel.Dispatcher.ClientOperation> クラスにアクセスを提供するクライアント動作を実装します。 これで、その動作の内部で、<xref:System.ServiceModel.Dispatcher.ClientRuntime> プロパティを要件に合わせて変更できるようになります。  
  
 通常は、操作動作 (<xref:System.ServiceModel.Description.IOperationBehavior> を実装するオブジェクト) の実装で十分ですが、エンドポイント動作とコントラクト動作を使用して、特定の操作の <xref:System.ServiceModel.Description.OperationDescription> を検索し、これに動作を関連付けても同じことを実現できます。 詳細については、「[を構成して、ランタイムのビヘイビアーの使用を拡張する](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)です。  
  
 構成からカスタム動作を使用するには、カスタム動作構成セクション ハンドラーを使用して動作をインストールします。 また、カスタム属性を作成することによって動作をインストールすることもできます。  
  
 間での傍受を示す例については、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]クライアントを参照してください[する方法: 検査パラメーターまたは変更](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-parameters.md)です。  
  
## <a name="see-also"></a>参照  
 <xref:System.ServiceModel.Dispatcher.ClientRuntime>  
 <xref:System.ServiceModel.Dispatcher.ClientOperation>  
 [方法 : クライアントのメッセージを検査または変更する](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md)  
 [方法 : パラメーターを検査または変更する](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-parameters.md)
