---
title: "Windows サービス アプリケーションの概要"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ServiceController
helpviewer_keywords:
- Windows Service applications, deploying
- OnStop method
- OnPause method
- services, about services
- Service class, Windows Service applications
- framework services, creating services
- ServiceController components, about Windows services
- Win32OwnProcess service type
- services, lifetime
- OnContinue method
- Windows Service applications, about Windows Service applications
- services, states
- service states
- WaitForStatus method
- Win32ShareProcess service type
- Windows Service applications, lifetime
ms.assetid: 1b1b5e67-3ff3-40c0-8154-322cfd6ef0ae
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 613107a13820ad71b854dcba93f21c41f2a5fa5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="introduction-to-windows-service-applications"></a>Windows サービス アプリケーションの概要
Microsoft Windows サービス (旧 NT サービス) を使用すると、Microsoft Windows サービス自体の Windows セッションで長時間にわたって実行されるアプリケーションを作成できます。 作成したサービスは、コンピューターのブート時に自動的に起動させることができます。また、サービスを一時停止したり、再起動したりすることもできます。このサービスはユーザー インターフェイスを表示しません。 このような特徴があるため、サービスはサーバー上で使用するのに適しており、コンピューターを共用する他のユーザーの邪魔をせずに長時間稼動させる機能を実現するのに最適です。 また、ログオン ユーザーや既定のコンピューター アカウントとは異なる、特定のユーザー アカウントのセキュリティ コンテキストでサービスを実行することもできます。 サービスと Windows セッションの詳細については、Windows SDK のマニュアルを参照してください。  
  
 サービスは、サービスとしてインストールするアプリケーションを作成することで簡単に作成できます。 たとえば、パフォーマンス カウンターのデータを監視し、しきい値を基準にした処理を行うとします。 この場合、パフォーマンス カウンターのデータを取得する Windows サービス アプリケーションを作成し配置して、データの収集と分析を行うことができます。  
  
 サービスは、Microsoft Visual Studio のプロジェクトとして作成します。サービスには、サービスに送信できるコマンドと、コマンド受信時に行うアクションとを制御するコードを定義します。 サービスに送信できるコマンドには、サービスの起動コマンド、一時停止コマンド、再開コマンド、および停止コマンドがあります。また、カスタム コマンドも実行できます。  
  
 アプリケーションを作成してビルドした後に、コマンド ライン ユーティリティの InstallUtil.exe を実行してサービスの実行可能ファイルのパスを指定することで、アプリケーションをインストールできます。 使用してできます、**サービス コントロール マネージャー**開始、停止、一時停止、再開、およびサービスを構成します。 これら同じタスクの多くを行うこともできます、 **Services**内のノード**サーバー エクスプ ローラー**またはを使用して、<xref:System.ServiceProcess.ServiceController>クラスです。  
  
## <a name="service-applications-vs-other-visual-studio-applications"></a>サービス アプリケーションとします。その他の Visual Studio アプリケーション  
 サービス アプリケーションの動作は、次に示すように、他のプロジェクトと異なります。  
  
-   サービス アプリケーション プロジェクトが作成するコンパイル済み実行可能ファイルは、プロジェクトの使用開始前にサーバーにインストールしておく必要があります。 F5 キーまたは F11 キーを押してサービス アプリケーションをデバッグまたは実行することはできません。サービスを即時に実行したり、サービスのコードにステップ インすることはできません。 サービスのインストールと起動を行ってから、デバッガーをサービスのプロセスにアタッチする必要があります。 詳細については、次を参照してください。[する方法: Windows サービス アプリケーションのデバッグ](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)です。  
  
-   一部のプロジェクトの場合とは異なり、サービス アプリケーションのインストール コンポーネントは必ず作成する必要があります。 インストールして、サーバー上のサービスを登録し、Windows では、サービスのエントリを作成のインストール コンポーネント**サービス コントロール マネージャー**です。 詳細については、次を参照してください。[する方法: サービス アプリケーションへのインストーラーの追加](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)です。  
  
-   サービス アプリケーションの `Main` メソッドは、プロジェクトに含まれているサービスの Run コマンドを実行する必要があります。 `Run`メソッドにサービスを読み込む、**サービス コントロール マネージャー**該当するサーバー。 使用する場合、 **Windows Services**プロジェクト テンプレートでは、このメソッドを自動的に書き込まれます。 サービスの読み込みとサービスの起動は異なります。 詳細については、後述の「サービスの有効期間」を参照してください。  
  
-   Windows サービス アプリケーションは、ログオン ユーザーの対話型ステーションとは異なるウィンドウ ステーションで実行されます。 ウィンドウ ステーションは、クリップボード、グローバルなアトムのセット、およびデスクトップ オブジェクトのグループを含む安全なオブジェクトです。 Windows サービスのステーションは対話型ステーションではないので、Windows サービス アプリケーションから出力されたダイアログ ボックスは表示されず、プログラムの応答が停止することがあります。 同様に、エラー メッセージもユーザー インターフェイスに出力されるのではなく、Windows イベント ログに記録されます。  
  
     .NET Framework でサポートされている Windows サービスのクラスは、対話型ステーション、つまりログオン ユーザーとの対話をサポートしていません。 また、.NET Framework には、ステーションおよびデスクトップを表すクラスが含まれていません。 Windows サービスが他のステーションと対話する必要がある場合は、アンマネージ Windows API にアクセスする必要があります。 詳細については、Windows SDK ドキュメントを参照してください。  
  
     Windows サービスとユーザーまたは他のステーションとの対話は、ログオン ユーザーがいない場合やユーザーが予期しないデスクトップ オブジェクトのセットを持っている場合などのシナリオにも対応できるように注意してデザインする必要があります。 場合によっては、ユーザーの制御下で実行される Windows アプリケーションを書いた方がより適切であることもあります。  
  
-   Windows サービス アプリケーションは、独自のセキュリティ コンテキストで実行され、Windows サービス アプリケーションがインストールされている Windows コンピューターにユーザーがログインする前に起動されます。 サービスを実行するユーザー アカウントは慎重に検討する必要があります。システム アカウントで実行されるサービスには、ユーザー アカウントで実行される場合より多くのアクセス許可とアクセス特権が認められます。  
  
## <a name="service-lifetime"></a>サービスの有効期間  
 サービスの内部状態は、有効期間内でさまざまに変化します。 まず初めに、サービスを実行するシステムにインストールされます。 このプロセスは、サービス プロジェクトのインストーラーが実行されにサービスを読み込み、**サービス コントロール マネージャー**そのコンピューターにします。 **サービス コントロール マネージャー**は、サービスを管理する Windows の中核となるユーティリティです。  
  
 サービスが読み込まれた後で、サービスを起動します。 サービスを起動すると、サービスが動作できるようになります。 サービスを開始することができます、**サービス コントロール マネージャー**から**サーバー エクスプ ローラー**、またはコードを呼び出してから、<xref:System.ServiceProcess.ServiceController.Start%2A>メソッドです。 <xref:System.ServiceProcess.ServiceController.Start%2A> メソッドは、処理をアプリケーションの <xref:System.ServiceProcess.ServiceBase.OnStart%2A> メソッドに渡し、このメソッドに定義されている処理を実行します。  
  
 実行中のサービスは、サービスの停止や一時停止が指示されたり、コンピューターがシャットダウンされるまで、実行中の状態を維持できます。 サービスの基本的な状態は、<xref:System.ServiceProcess.ServiceControllerStatus.Running>、<xref:System.ServiceProcess.ServiceControllerStatus.Paused>、または <xref:System.ServiceProcess.ServiceControllerStatus.Stopped> です。 サービスは保留中のコマンドの状態 (<xref:System.ServiceProcess.ServiceControllerStatus.ContinuePending>、<xref:System.ServiceProcess.ServiceControllerStatus.PausePending>、<xref:System.ServiceProcess.ServiceControllerStatus.StartPending>、または <xref:System.ServiceProcess.ServiceControllerStatus.StopPending>) も報告できます。 これらの状態は、実行中のサービスを一時停止するコマンドなどが実行されたが、まだ完了していない状態を表します。 <xref:System.ServiceProcess.ServiceController.Status%2A> を問い合わせるとサービスがどの状態にあるかを判別でき、<xref:System.ServiceProcess.ServiceController.WaitForStatus%2A> を使用するとこのいずれかの状態になったときに処理を実行できます。  
  
 一時停止、停止、またはからサービスを再開することができます、**サービス コントロール マネージャー**から**サーバー エクスプ ローラー**、またはコードでメソッドを呼び出しています。 これらのアクションは、サービスの中でそれぞれ対応するプロシージャ (<xref:System.ServiceProcess.ServiceBase.OnStop%2A>、<xref:System.ServiceProcess.ServiceBase.OnPause%2A>、または <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>) を呼び出すことができます。これらのプロシージャには、サービスの状態が変化したときに実行する追加処理を定義できます。  
  
## <a name="types-of-services"></a>サービスの種類  
 Visual Studio で .NET Framework を使用して作成できるサービスには 2 種類あります。 プロセスを占有するサービスには、<xref:System.ServiceProcess.ServiceType.Win32OwnProcess> 型が割り当てられます。 他のサービスとプロセスを共有するサービスには、<xref:System.ServiceProcess.ServiceType.Win32ShareProcess> 型が割り当てられます。 サービスの種類は、<xref:System.ServiceProcess.ServiceController.ServiceType%2A> プロパティを問い合わせて取得できます。  
  
 Visual Studio 以外で作成された既存のサービスを問い合わせた場合は、これ以外のサービスの種類が割り当てられていることもあります。 それらの詳細については、「<xref:System.ServiceProcess.ServiceType>」を参照してください。  
  
## <a name="services-and-the-servicecontroller-component"></a>サービスと ServiceController コンポーネント  
 <xref:System.ServiceProcess.ServiceController> コンポーネントは、インストール済みのサービスに接続し、サービスの状態を操作するときに使用します。<xref:System.ServiceProcess.ServiceController> コンポーネントを使用すると、サービスの起動と停止、およびサービスの一時停止と継続を実行できます。また、カスタム コマンドをサービスに送信することもできます。 ただし、サービス アプリケーションを作成する場合は、<xref:System.ServiceProcess.ServiceController> コンポーネントを使用する必要はありません。 ほとんどの場合は、サービスを定義している Windows サービス アプリケーションとは別のアプリケーションに <xref:System.ServiceProcess.ServiceController> コンポーネントが含まれています。  
  
 詳細については、「<xref:System.ServiceProcess.ServiceController>」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
-   サービスを作成する必要があります、 **Windows サービス**アプリケーション プロジェクトまたは別の .NET Framework – 有効になっているプロジェクトをビルド時に、.exe ファイルを作成し、継承、<xref:System.ServiceProcess.ServiceBase>クラスです。  
  
-   Windows サービスを含むプロジェクトには、プロジェクトのインストール コンポーネントと、プロジェクトのサービスのインストール コンポーネントが必要です。 これから簡単に実現することができます、**プロパティ**ウィンドウです。 詳細については、次を参照してください。[する方法: サービス アプリケーションへのインストーラーの追加](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)です。  
  
## <a name="see-also"></a>参照  
 [Windows サービス アプリケーション](../../../docs/framework/windows-services/index.md)  
 [サービス アプリケーションのプログラミング アーキテクチャ](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 [方法 : Windows サービスを作成する](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [方法 : サービスをインストールおよびアンインストールする](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [方法 : サービスを開始する](../../../docs/framework/windows-services/how-to-start-services.md)  
 [方法 : Windows サービス アプリケーションをデバッグする](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [チュートリアル: コンポーネント デザイナーによる Windows サービス アプリケーションの作成](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 [方法 : サービス アプリケーションにインストーラーを追加する](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
