---
title: "カスタム追跡 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2d191c9f-62f4-4c63-92dd-cda917fcf254
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# カスタム追跡
このサンプルでは、カスタムの追跡参加要素を作成し、追跡データをコンソールに出力する方法を示します。また、ユーザー定義データが設定された <xref:System.Activities.Tracking.CustomTrackingRecord> オブジェクトを出力する方法も示します。コンソール ベースの追跡参加要素は、コードで作成された追跡プロファイル オブジェクトを使用して、ワークフローで出力された <xref:System.Activities.Tracking.TrackingRecord> オブジェクトをフィルター処理します。  
  
## サンプルの詳細  
 [!INCLUDE[wf](../../../../includes/wf-md.md)] には、ワークフロー インスタンスの実行を追跡できる追跡インフラストラクチャが用意されています。追跡ランタイムは、ワークフロー ライフサイクルに関連するイベント、ワークフロー アクティビティのイベント、およびカスタム追跡イベントを出力するワークフロー インスタンスを実装しています。次の表で、追跡インフラストラクチャの主要コンポーネントの詳細を説明します。  
  
|コンポーネント|説明|  
|-------------|--------|  
|追跡ランタイム|追跡レコードを出力するためのインフラストラクチャを提供します。|  
|追跡参加要素|追跡レコードを処理します。[!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] には、追跡レコードを Event Tracing for Windows \(ETW\) イベントとして書き込む追跡参加要素が用意されています。|  
|追跡プロファイル|ワークフロー インスタンスから出力された追跡レコードのサブセットを追跡参加要素から定期受信するためのフィルター機構。|  
  
 次の表で、ワークフロー ランタイムが出力する追跡レコードの詳細を説明します。  
  
|追跡レコード|説明|  
|------------|--------|  
|ワークフロー インスタンスの追跡レコード|ワークフロー インスタンスのライフサイクルを表します。たとえば、ワークフローの開始時または完了時にインスタンス レコードが出力されます。|  
|アクティビティ状態の追跡レコード|アクティビティの実行状況を詳しく記録します。これらのレコードは、アクティビティをスケジュールしたとき、アクティビティが完了したとき、エラーがスローされたときなど、ワークフロー アクティビティの状態を示します。|  
|ブックマーク再開レコード|ワークフロー インスタンス内のブックマークが再開されたときに出力されます。|  
|カスタム追跡レコード|ワークフロー作成者はカスタム追跡レコードを作成し、カスタム アクティビティ内で出力できます。|  
  
 追跡参加要素は、追跡プロファイルを使用して、出力された <xref:System.Activities.Tracking.TrackingRecord> オブジェクトのサブセットを定期受信します。追跡プロファイルには、特定の追跡レコード タイプを定期受信するための追跡クエリが含まれています。追跡プロファイルは、コードで指定したり、構成で指定したりすることができます。  
  
### カスタムの追跡参加要素  
 追跡参加要素 API では、ワークフロー ランタイムが出力する <xref:System.Activities.Tracking.TrackingRecord> オブジェクトを処理するためのカスタム ロジックを含めることが可能なユーザー指定の追跡参加要素を使用して、追跡ランタイムを拡張できます。  
  
 追跡参加要素を書き込むには、ユーザーは <xref:System.Activities.Tracking.TrackingParticipant> を実装する必要があります。具体的には、カスタム参加要素で <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> メソッドを実装する必要があります。このメソッドは、ワークフロー ランタイムによって <xref:System.Activities.Tracking.TrackingRecord> が出力されるときに呼び出されます。  
  
```csharp  
public abstract class TrackingParticipant  
{  
    protected TrackingParticipant();  
  
    public virtual TrackingProfile TrackingProfile { get; set; }  
    public abstract void Track(TrackingRecord record, TimeSpan timeout);  
}  
  
```  
  
 完全な追跡参加要素は ConsoleTrackingParticipant.cs ファイルで実装します。次のコード例は、カスタム追跡参加要素の <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> メソッドです。  
  
```csharp  
protected override void Track(TrackingRecord record, TimeSpan timeout)  
{  
    ...             
    WorkflowInstanceRecord workflowInstanceRecord = record as WorkflowInstanceRecord;  
    if (workflowInstanceRecord != null)  
    {  
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,  
            " Workflow InstanceID: {0} Workflow instance state: {1}",  
            record.InstanceId, workflowInstanceRecord.State));  
    }  
  
    ActivityStateRecord activityStateRecord = record as ActivityStateRecord;  
    if (activityStateRecord != null)  
    {  
        IDictionary<String, object> variables = activityStateRecord.Variables;  
        StringBuilder vars = new StringBuilder();  
  
        if (variables.Count > 0)  
        {  
            vars.AppendLine("\n\tVariables:");  
            foreach (KeyValuePair<string, object> variable in variables)  
            {     
                vars.AppendLine(String.Format(  
                    "\t\tName: {0} Value: {1}", variable.Key, variable.Value));  
            }  
        }  
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,  
            " :Activity DisplayName: {0} :ActivityInstanceState: {1} {2}",  
                activityStateRecord.Activity.Name, activityStateRecord.State,  
            ((variables.Count > 0) ? vars.ToString() : String.Empty)));  
    }  
  
    CustomTrackingRecord customTrackingRecord = record as CustomTrackingRecord;  
  
    if ((customTrackingRecord != null) && (customTrackingRecord.Data.Count > 0))  
    {  
        ...  
    }  
    Console.WriteLine();  
  
}  
  
```  
  
 次のコード例では、ワークフローの呼び出し元にコンソール参加要素を追加します。  
  
```csharp  
ConsoleTrackingParticipant customTrackingParticipant = new ConsoleTrackingParticipant()  
{  
    ...  
    // The tracking profile is set here, refer to Program.CS  
...  
}  
  
WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());  
invoker.Extensions.Add(customTrackingParticipant);  
  
```  
  
### カスタム追跡レコードの出力  
 このサンプルでは、カスタム ワークフロー アクティビティから <xref:System.Activities.Tracking.CustomTrackingRecord> オブジェクトを出力する機能も示します。  
  
-   <xref:System.Activities.Tracking.CustomTrackingRecord> オブジェクトは、レコードと一緒に出力する必要があるユーザー定義データを使用して作成および設定します。  
  
-   <xref:System.Activities.Tracking.CustomTrackingRecord> を出力するには、<xref:System.Activities.ActivityContext> の追跡メソッドを呼び出します。  
  
 次の例では、カスタム アクティビティ内で <xref:System.Activities.Tracking.CustomTrackingRecord> オブジェクトを出力する方法を示します。  
  
```csharp  
// Create the Custom Tracking Record  
CustomTrackingRecord customRecord = new CustomTrackingRecord("OrderIn")  
{  
    Data =   
    {  
        {"OrderId", 200},  
        {"OrderDate", "20 Aug 2001"}  
    }  
};  
  
// Emit custom tracking record  
context.Track(customRecord);  
  
```  
  
#### このサンプルを使用するには  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] を使用して、CustomTrackingSample.sln ソリューション ファイルを開きます。  
  
2.  ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。  
  
3.  ソリューションを実行するには、Ctrl キーを押しながら F5 キーを押します。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。続行する前に、次の \(既定の\) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合は、「[.NET Framework 4 向けの Windows Communication Foundation \(WCF\) および Windows Workflow Foundation \(WF\) のサンプル](http://go.microsoft.com/fwlink/?LinkId=150780)」にアクセスして、[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] および [!INCLUDE[wf1](../../../../includes/wf1-md.md)] のサンプルをすべてダウンロードしてください。このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\CustomTracking`  
  
## 参照  
 [AppFabric の監視のサンプル](http://go.microsoft.com/fwlink/?LinkId=193959)