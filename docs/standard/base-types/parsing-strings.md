---
title: ".NET での文字列の解析"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9c2193dd1b1f3c0478efb5fc9c2b80250ef1878f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/23/2017
---
# <a name="parsing-strings-in-net"></a>.NET での文字列の解析
解析操作では、.NET の基本データ型を表す文字列をその基本データ型に変換します。 たとえば解析操作は、文字列を浮動小数点数や日付と時刻の値に変換するために使用します。 解析操作を実行するには、`Parse` メソッドがよく使用されます。 解析は書式設定の逆の操作 (基本データ型のその文字列形式への変換を含む) であるため、多くの同じ規則が適用されます。 カルチャに依存する書式情報を指定するために、書式設定で <xref:System.IFormatProvider> インターフェイスを実装するオブジェクトを使用するのと同じように、解析でも <xref:System.IFormatProvider> インターフェイスを実装するオブジェクトを使用し、文字列形式を解釈する方法を決定します。 詳細については、[型の書式設定](../../../docs/standard/base-types/formatting-types.md)に関するページをご覧ください。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [数値文字列の解析](../../../docs/standard/base-types/parsing-numeric.md)  
 文字列を .NET 数値型に変換する方法について説明します。  
  
 [日付と時刻文字列の解析](../../../docs/standard/base-types/parsing-datetime.md)  
 文字列を .NET **DateTime** 型に変換する方法について説明します。  
  
 [その他の文字列の解析](../../../docs/standard/base-types/parsing-other.md)  
 文字列を **Char** 型、**Boolean** 型、**Enum** 型に変換する方法について説明します。  
  
## <a name="related-sections"></a>関連項目  
 [型の書式設定](../../../docs/standard/base-types/formatting-types.md)  
 書式指定子や書式プロバイダーなどの基本書式の概念について説明します。  
  
 [.NET での型変換](../../../docs/standard/base-types/type-conversion.md)  
 型に変換する方法について説明します。  
  
 [基本データ型](../../../docs/standard/base-types/index.md)  
 .NET の基本型で実行できる一般的な操作について説明します。
