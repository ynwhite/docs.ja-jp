---
title: "デリゲート クラス &#39;&lt;classname&gt;&#39; この型の式はメソッドの呼び出しのターゲットにすることはできませんので Invoke メソッドがありません"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords: BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 55d0e2442807e25737d90ac4b45a59b9d3e73037
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>デリゲート クラス &#39;&lt;classname&gt;&#39; この型の式はメソッドの呼び出しのターゲットにすることはできませんので Invoke メソッドがありません
呼び出し`Invoke`がデリゲートから失敗しました。`Invoke`デリゲート クラスで実装されていません。  
  
 **エラー ID:** BC30220  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  デリゲート クラスのインスタンスが作成されたことを確認してください、`Dim`ステートメントと、プロシージャがデリゲートのインスタンスに割り当てられている、`AddressOf`演算子。  
  
2.  デリゲート クラスを実装するコードを検索しを実装するかどうかを確認、`Invoke`プロシージャです。  
  
## <a name="see-also"></a>関連項目  
 [デリゲート](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Delegate ステートメント](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [AddressOf 演算子](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Dim ステートメント](../../../visual-basic/language-reference/statements/dim-statement.md)
