---
title: ".NET Framework 4.5.2 における再ターゲットの変更点 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2be2a828-9052-4738-a965-d4a836cc6384
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# .NET Framework 4.5.2 における再ターゲットの変更点
まれに、変更を再ターゲットすると .NET Framework 4.5.2 を対象として再コンパイルされるアプリに影響する場合があります。 次の表で別途指定がない限り、これらの変化は、以前のバージョンの .NET Framework を対象とするものの、Version 4.5.2 で実行されるバイナリには影響を与えません。 .NET Framework 4.5.2 には、次の領域の変更の再ターゲットが含まれます。  
  
-   [Entity Framework](#EF)  
  
-   [Windows フォーム](#WinForms)  
  
<a name="EF"></a>   
## Entity Framework の変更の再ターゲット  
  
|機能|変更|影響|スコープ|  
|--------|--------|--------|----------|  
|並べ替えられていない制限操作を使用する際のより単純なクエリ|最初に `JOIN` を使用せずに <xref:System.Data.Objects.ObjectQuery%601.OrderBy%2A> ステートメントを生成し、制限操作への呼び出しを含むクエリは、より単純な SQL を生成します。[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] へのアップグレード後、これらのクエリは以前のバージョンよりも複雑な SQL を生成しました。|既定では、この機能は無効です。 Entity Framework がパフォーマンスを低下させる追加の `JOIN` ステートメントを生成する場合は、アプリケーション構成 \(app.config\) ファイルの `<appSettings>` セクションへ次のエントリを追加してこの機能を有効にできます。<br /><br /> `<add key="EntityFramework_SimplifyLimitOperations" value="true" />`|マイナー|  
  
<a name="WinForms"></a>   
## Windows フォームの変更の再ターゲット  
  
|機能|変更|影響|スコープ|  
|--------|--------|--------|----------|  
|<xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName> メソッドを使用してクリップボードからデータを HTML 形式で取得する|[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] を対象とするアプリまたは .NET Framework 4.5.1 以前のバージョンで実行されるアプリでは、<xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName> は HTML 形式のデータを ASCII 文字列として取得します。 結果として、非 ASCII 文字 \(ASCII コードが 0x7F よりも大きい文字\) は 2 つのランダムな文字で表されます。 たとえば、「é \(0xE9\)」は「Ã© \(0xC3 0xA9\)」により表されます。<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 以降を対象とするアプリまたは .NET Framework 4.5.2 で実行されるアプリでは、<xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName> は HTML 形式のデータを UTF\-8 として取得します。これは、0x7F よりも大きい文字を正しく表しています。|HTML 形式の文字列を使用するエンコーディングの問題に対する回避策 \(例: クリップボードから取得した HTML 文字列を <xref:System.Text.UTF8Encoding.GetString%2A?displayProperty=fullName> メソッドに渡して明示的にエンコードすること\) を実装し、アプリをバージョン 4 から 4.5 へ再ターゲットしている場合は、その回避策を削除する必要があります。|マイナー|  
  
## 参照  
 [ランタイムの変更点](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-2.md)   
 [4.5 のアプリケーションの互換性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [4.5.1 のアプリケーションの互換性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)