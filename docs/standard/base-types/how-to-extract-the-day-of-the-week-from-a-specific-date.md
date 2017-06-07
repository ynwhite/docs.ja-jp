---
title: "方法 : 特定の日付から曜日を抽出する | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "書式指定 [.NET Framework]、日付"
  - "DateTime.DayOfWeek プロパティ"
  - "DateTime.ToString メソッド"
  - "日付 [.NET Framework], 週の情報を取得する"
  - "DateTimeOffset.DayOfWeek プロパティ"
  - "日付 [.NET Framework], 曜日"
  - "Weekday 関数"
  - "曜日 [.NET Framework]"
  - "抽出 (曜日を)"
  - "曜日の名前"
  - "WeekdayName 関数"
  - "数値 [.NET Framework], 曜日"
  - "書式指定 [.NET Framework], 時刻"
  - "DateTimeOffset.ToString メソッド"
  - "曜日の正式名"
ms.assetid: 1c9bef76-5634-46cf-b91c-9b9eb72091d7
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 方法 : 特定の日付から曜日を抽出する
.NET Framework では、特定の日付が週の何日目であるかを容易に判別でき、また特定の日付のローカライズされた曜日名を表示できます。 特定の日付に対応する曜日を示す列挙値は、<xref:System.DateTime.DayOfWeek%2A> または <xref:System.DateTimeOffset.DayOfWeek%2A> プロパティから取得できます。 対照的に、曜日名の取得は、書式指定メソッド （日付と時刻の値の `ToString` メソッドや <xref:System.String.Format%2A?displayProperty=fullName> メソッドなど） を呼び出して実行できる書式指定操作です。 このトピックでは、このような書式指定操作を実行する方法について説明します。  
  
### 特定の日付から曜日を示す番号を抽出するには  
  
1.  文字列形式の日付を処理している場合には、静的 <xref:System.DateTime> または <xref:System.DateTimeOffset> メソッドを使用して、その日付を<xref:System.DateTime.Parse%2A?displayProperty=fullName> 値または <xref:System.DateTimeOffset.Parse%2A?displayProperty=fullName> 値に変換します。  
  
2.  <xref:System.DateTime.DayOfWeek%2A?displayProperty=fullName> プロパティまたは <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=fullName> プロパティを使用して、曜日を示す <xref:System.DayOfWeek> 値を取得します。  
  
3.  必要に応じて、<xref:System.DayOfWeek> 値を整数にキャスト （C\#） または変換 （Visual Basic） します。  
  
 次の例は、特定の日付の曜日を表す整数を表示します。  
  
 [!code-csharp[Formatting.Howto.WeekdayName#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/weekdaynumber7.cs#7)]
 [!code-vb[Formatting.Howto.WeekdayName#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/weekdaynumber7.vb#7)]  
  
### 特定の日付から曜日の省略名を抽出するには  
  
1.  文字列形式の日付を処理している場合には、静的 <xref:System.DateTime> または <xref:System.DateTimeOffset> メソッドを使用して、その日付を<xref:System.DateTime.Parse%2A?displayProperty=fullName> 値または <xref:System.DateTimeOffset.Parse%2A?displayProperty=fullName> 値に変換します。  
  
2.  次の手順で現在のカルチャまたは特定のカルチャの曜日の省略名を抽出できます。  
  
    1.  現在のカルチャの曜日の省略名を抽出するには、日付と時刻の値の <xref:System.DateTime.ToString%28System.String%29?displayProperty=fullName> インスタンス メソッドまたは <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=fullName> インスタンス メソッドを呼び出し、`format` パラメーターとして文字列 "ddd" を渡します。 次の例に、<xref:System.DateTime.ToString%28System.String%29> メソッドの呼び出しを示します。  
  
         [!code-csharp[Formatting.Howto.WeekdayName#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname1.cs#1)]
         [!code-vb[Formatting.Howto.WeekdayName#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname1.vb#1)]  
  
    2.  特定のカルチャの曜日の省略名を抽出するには、日付と時刻の値の <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=fullName> インスタンス メソッドまたは <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=fullName> インスタンス メソッドを呼び出します。`format` パラメーターとして文字列 "ddd" を渡します。 曜日名を取得するカルチャを表す <xref:System.Globalization.CultureInfo> または <xref:System.Globalization.DateTimeFormatInfo> オブジェクトのいずれかを`provider` パラメーターとして渡します。 次のコードは、fr\-FR カルチャを表す <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> オブジェクトを使用した <xref:System.Globalization.CultureInfo> メソッドの呼び出しを示します。  
  
         [!code-csharp[Formatting.Howto.WeekdayName#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname2.cs#2)]
         [!code-vb[Formatting.Howto.WeekdayName#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname2.vb#2)]  
  
### 特定の日付から曜日の正式な名前を抽出するには  
  
1.  文字列形式の日付を処理している場合には、静的 <xref:System.DateTime> または <xref:System.DateTimeOffset> メソッドを使用して、その日付を<xref:System.DateTime.Parse%2A?displayProperty=fullName> 値または <xref:System.DateTimeOffset.Parse%2A?displayProperty=fullName> 値に変換します。  
  
2.  現在のカルチャまたは特定のカルチャでの曜日の正式な名前を抽出できます。  
  
    1.  現在のカルチャの曜日名を抽出するには、日付と時刻の値の <xref:System.DateTime.ToString%28System.String%29?displayProperty=fullName> インスタンス メソッドまたは <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=fullName> インスタンス メソッドを呼び出し、`format` パラメーターとして文字列 "dddd" を渡します。 次の例に、<xref:System.DateTime.ToString%28System.String%29> メソッドの呼び出しを示します。  
  
         [!code-csharp[Formatting.Howto.WeekdayName#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname4.cs#4)]
         [!code-vb[Formatting.Howto.WeekdayName#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname4.vb#4)]  
  
    2.  特定のカルチャの曜日名を抽出するには、日付と時刻の値の <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=fullName> インスタンス メソッドまたは <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=fullName> インスタンス メソッドを呼び出します。`format` パラメーターとして文字列 "dddd" を渡します。 曜日名を取得するカルチャを表す <xref:System.Globalization.CultureInfo> または <xref:System.Globalization.DateTimeFormatInfo> オブジェクトのいずれかを`provider` パラメーターとして渡します。 次のコードは、es\-ES カルチャを表す <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> オブジェクトを使用した <xref:System.Globalization.CultureInfo> メソッドの呼び出しを示します。  
  
         [!code-csharp[Formatting.Howto.WeekdayName#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname5.cs#5)]
         [!code-vb[Formatting.Howto.WeekdayName#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname5.vb#5)]  
  
## 使用例  
 この例は、<xref:System.DateTime.DayOfWeek%2A?displayProperty=fullName> プロパティと<xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=fullName> プロパティ、および<xref:System.DateTime.ToString%2A?displayProperty=fullName> メソッドと <xref:System.DateTimeOffset.ToString%2A?displayProperty=fullName> メソッドを呼び出し、特定の日付の曜日を表す番号、曜日の省略名、および正式な名前を取得します。  
  
 [!code-csharp[Formatting.Howto.WeekdayName#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/example6.cs#6)]
 [!code-vb[Formatting.Howto.WeekdayName#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example6.vb#6)]  
  
 それぞれの言語には、[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] の機能と重複する機能または補足する機能が存在していることがあります。 たとえば Visual Basic には次の 2 つの関数があります。  
  
-   `Weekday`: 特定の日付の曜日を示す番号を返します。 この関数では週の初日の序数値が 1 ですが、<xref:System.DateTime.DayOfWeek%2A?displayProperty=fullName> プロパティでは週の初日の序数値はゼロです。  
  
-   `WeekdayName`: 現在のカルチャで、特定の曜日番号に対応する曜日名を返します。  
  
 次の例は、Visual Basic の `Weekday` 関数と `WeekdayName` 関数の使い方を示します。  
  
 [!code-vb[Formatting.HowTo.WeekdayName#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example9.vb#9)]  
  
 また、特定の日付の曜日名を取得するには <xref:System.DateTime.DayOfWeek%2A?displayProperty=fullName> プロパティから返される値も使用できます。 このためには、プロパティから返された <xref:System.Enum.ToString%2A> 値に対して <xref:System.DayOfWeek> メソッドを呼び出す操作だけが必要です。 ただしこの手法では、次の例に示すように、現在のカルチャでのローカライズされた曜日名は作成されません。  
  
 [!code-csharp[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/Howto1.cs#8)]
 [!code-vb[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/Howto1.vb#8)]  
  
## 参照  
 [書式設定操作の実行](../../../docs/standard/base-types/performing-formatting-operations.md)   
 [標準の日時書式指定文字列](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)   
 [カスタム日時書式指定文字列](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)