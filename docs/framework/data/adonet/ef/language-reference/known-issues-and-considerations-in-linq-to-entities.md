---
title: "LINQ to Entities の既知の問題および注意点"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: dd45bc4f2229237c50e9bfda36e5fb18512f9ef0
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="known-issues-and-considerations-in-linq-to-entities"></a>LINQ to Entities の既知の問題および注意点
ここでは、[!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] クエリの既知の問題について説明します。  
  
-   [LINQ クエリをキャッシュできないこと](#LINQQueriesThatAreNotCached)  
  
-   [失われた情報を順序付け](#OrderingInfoLost)  
  
-   [符号なし整数がサポートされていません](#UnsignedIntsUnsupported)  
  
-   [型変換エラー](#TypeConversionErrors)  
  
-   [参照元の非スカラー変数がサポートされていません](#RefNonScalarClosures)  
  
-   [入れ子になったクエリは、SQL Server 2000 で失敗する可能性があります。](#NestedQueriesSQL2000)  
  
-   [匿名型に射影](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>   
## <a name="linq-queries-that-cannot-be-cached"></a>キャッシュできない LINQ クエリ  
 .NET Framework 4.5 以降では、LINQ to Entities クエリは自動的にキャッシュされます。 ただし、メモリ内コレクションへ `Enumerable.Contains` 演算子を追加する LINQ to Entities クエリは自動的にキャッシュされません。 またコンパイル済み LINQ クエリのメモリ内コレクションをパラメーターで表すことは許可されていません。  
  
<a name="OrderingInfoLost"></a>   
## <a name="ordering-information-lost"></a>失われた情報の収集の順序付け  
 匿名型に列を投影すると、互換性レベルが "80" に設定された [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)] データベースに対して実行されるクエリの一部で順序付けが失われます。  この状況は、次の例に示すように、ORDER BY リストの列名がセレクターの列名と一致する場合に発生します。  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>   
## <a name="unsigned-integers-not-supported"></a>サポートされていない符号なし整数  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] によって符号なし整数がサポートされていないため、[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] クエリでの符号なし整数型の指定はサポートされていません。 符号なし整数を指定する場合、<xref:System.ArgumentException>次の例で示すようにクエリ式の変換中に例外がスローされます。 この例では、ID 48000 を持つ注文に対してクエリを実行します。  
  
 [!code-csharp[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#uintasqueryparam)]
 [!code-vb[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#uintasqueryparam)]  
  
<a name="TypeConversionErrors"></a>   
## <a name="type-conversion-errors"></a>型変換エラー  
 Visual Basic では、`CByte` 関数を使用して 1 の値を持つ SQL Server の bit 型の列にプロパティがマップされると、"算術オーバーフロー エラー" というメッセージと共に <xref:System.Data.SqlClient.SqlException> がスローされます。 次の例では、AdventureWorks サンプル データベースの `Product.MakeFlag` 列をクエリし、クエリ結果が反復処理されると、例外がスローされます。  
  
 [!code-vb[DP L2E Conceptual Examples#SBUDT544355](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt544355)]  
  
<a name="RefNonScalarClosures"></a>   
## <a name="referencing-non-scalar-variables-not-supported"></a>非スカラー変数の参照はサポートされていません。  
 クエリでの非スカラー変数 (エンティティなど) の参照はサポートされていません。 そのようなクエリを実行すると、<xref:System.NotSupportedException> 例外がスローされ、"型 `EntityType` の定数値を作成できません。 このコンテキストでサポートされるのはプリミティブ型 ('Int32、String、Guid など') だけです" というメッセージが表示されます。  
  
> [!NOTE]
>  スカラー変数のコレクションの参照はサポートされています。  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt555877)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt555877)]  
  
<a name="NestedQueriesSQL2000"></a>   
## <a name="nested-queries-may-fail-with-sql-server-2000"></a>入れ子になったクエリは、SQL Server 2000 では失敗する可能性があります。  
 SQL Server 2000 では、LINQ to Entities クエリは、3 ～ 4 レベルの深さの入れ子になった Transact-SQL クエリを生成する場合に失敗する可能性があります。  
  
<a name="ProjectToAnonymousType"></a>   
## <a name="projecting-to-an-anonymous-type"></a>匿名型への投影  
 <xref:System.Data.Objects.ObjectQuery%601.Include%2A> に <xref:System.Data.Objects.ObjectQuery%601> メソッドを使用して、関連オブジェクトを含めるように最初のクエリ パスを定義してから LINQ を使用して、返されたオブジェクトを匿名の型に投影した場合、include メソッドで指定されたオブジェクトはクエリ結果に含まれません。  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype1)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype1)]  
  
 関連オブジェクトを取得するには、返された型を匿名の型に投影しないでください。  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype2)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype2)]  
  
## <a name="see-also"></a>参照  
 [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
