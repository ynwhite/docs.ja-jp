---
title: "DataAdapter と DataReader"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3a7ce8787dec2f80ba04bef08c5ac355a907feaf
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="dataadapters-and-datareaders"></a>DataAdapter と DataReader
ADO.NET を使用する**DataReader**をデータベースからデータの読み取り専用、前方参照専用のストリームを取得します。 結果が返されるように、クエリが実行され、それらを要求するまで、クライアントのネットワーク バッファーに格納されますを使用して、**読み取り**のメソッド、 **DataReader**です。 使用して、 **DataReader** 、使用可能になるとすぐにデータを取得して (既定) の両方に、アプリケーションのパフォーマンスを向上できるメモリ、システムのオーバーヘッドを減らすことで、一度に 1 行のみを格納します。  
  
 <xref:System.Data.Common.DataAdapter> は、データ ソースからデータを取得し、1 つの <xref:System.Data.DataSet> 内でテーブルを設定するために使用されます。 また、`DataAdapter` は、`DataSet` に対して加えられた変更をデータ ソースに反映させます。 `DataAdapter` は .NET Framework データ プロバイダーの `Connection` オブジェクトを使用してデータ ソースに接続し、`Command` オブジェクトを使用してデータ ソースからデータを取得し、変更をデータ ソースに反映させます。  
  
 .NET Framework に含まれている各 .NET Framework データ プロバイダーには、<xref:System.Data.Common.DbDataReader> および <xref:System.Data.Common.DbDataAdapter> オブジェクトがあります.NET Framework Data Provider for OLE DB には <xref:System.Data.OleDb.OleDbDataReader> および <xref:System.Data.OleDb.OleDbDataAdapter> オブジェクトがあります.NET Framework Data Provider for SQL Server には <xref:System.Data.SqlClient.SqlDataReader> および <xref:System.Data.SqlClient.SqlDataAdapter> オブジェクトがあります.NET Framework Data Provider for ODBC には、<xref:System.Data.Odbc.OdbcDataReader> および <xref:System.Data.Odbc.OdbcDataAdapter> オブジェクトがあります.NET Framework Data Provider for Oracle には、<xref:System.Data.OracleClient.OracleDataReader> および <xref:System.Data.OracleClient.OracleDataAdapter> オブジェクトがあります。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [DataReader によるデータの取得](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 ADO.NET の説明**DataReader**オブジェクトと、ストリームを返す結果のデータ ソースから使用する方法です。  
  
 [DataAdapter からの DataSet の読み込み](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 `DataSet` を使用して `DataAdapter` にテーブル、列、および行を設定する方法について説明します。  
  
 [DataAdapter パラメーター](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 `DataAdapter` のコマンド プロパティのパラメーターを使用する方法と、`DataSet` の列の内容をコマンド パラメーターに割り当てる方法について説明します。  
  
 [DataSet への既存の制約の追加](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 既存の制約を `DataSet` に追加する方法について説明します。  
  
 [DataAdapter DataTable と DataColumn のマップ](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 `DataTableMappings` の `ColumnMappings` および `DataAdapter` を設定する方法について説明します。  
  
 [クエリ結果のページング](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 クエリの結果をデータ ページとして表示する例を示します。  
  
 [DataAdapter によるデータ ソースの更新](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 `DataAdapter` を使用して `DataSet` の変更内容を解決してデータベースに戻す方法について説明します。  
  
 [DataAdapter のイベント処理](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 `DataAdapter` のイベントおよびその使用方法について説明します。  
  
 [DataAdapter を使用したバッチ操作の実行](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 `DataSet` から更新を適用する際に、SQL Server へのラウンド トリップ回数を減らすことにより、アプリケーションのパフォーマンスを向上させる方法について説明します。  
  
## <a name="see-also"></a>参照  
 [データ ソースへの接続](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [コマンドおよびパラメーター](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [トランザクションと同時実行](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [DataSet、DataTable、および DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET のマネージ プロバイダーと DataSet デベロッパー センター](http://go.microsoft.com/fwlink/?LinkId=217917)
