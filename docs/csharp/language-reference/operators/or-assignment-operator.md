---
title: "|= 演算子 (C# リファレンス)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aac4fd6016b65daa15da4bd3a414f385edce7c22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>|= 演算子 (C# リファレンス)
OR 代入演算子です。  
  
## <a name="remarks"></a>コメント  
 次のような `|=` 代入演算子を使用する式があるとします  
  
```  
x |= y  
```  
  
 上記の式は、次の式と同じです。  
  
```  
x = x | y  
```  
  
 ただし、`x` が評価されるのは 1 回だけです。 [&#124; 演算子](../../../csharp/language-reference/operators/or-operator.md)では、整数のオペランドではビットごとの論理 OR 演算、ブール オペランドでは論理 OR 演算が実行されます。  
  
 `|=` 演算子は直接オーバーロードできませんが、ユーザー定義型は [&#124; 演算子](../../../csharp/language-reference/operators/or-operator.md)をオーバーロードできます (「[operator](../../../csharp/language-reference/keywords/operator.md)」参照)。  
  
## <a name="example"></a>例  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>関連項目  
 [C# リファレンス](../../../csharp/language-reference/index.md)  
 [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
 [C# 演算子](../../../csharp/language-reference/operators/index.md)
