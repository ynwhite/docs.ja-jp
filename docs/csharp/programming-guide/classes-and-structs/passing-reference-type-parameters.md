---
title: "参照型パラメーターの引き渡し (C# プログラミング ガイド)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- method parameters [C#], reference types
- parameters [C#], reference
ms.assetid: 9e6eb65c-942e-48ab-920a-b7ba9df4ea20
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 282929d82822f81f12dae91d2f422da51a0f43e5
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="passing-reference-type-parameters-c-programming-guide"></a>参照型パラメーターの引き渡し (C# プログラミング ガイド)
[型参照](../../../csharp/language-reference/keywords/reference-types.md)の変数には、そのデータは直接含まれず、そのデータへの参照が含まれます。 値で参照型パラメーターを渡す場合、クラス メンバーの値など、参照先オブジェクトに属するデータを変更することができます。 ただし、参照自体の値を変更することはできません。たとえば、同じ参照を使用して、新しいクラスのメモリを割り当て、ブロックの外側で永続化させることはできません。 これを行うには、[ref](../../../csharp/language-reference/keywords/ref.md) または [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) キーワードを使用してパラメーターを渡します。 わかりやすくするために、次の例では `ref` を使用しています。  
  
## <a name="passing-reference-types-by-value"></a>値渡しによる参照型の引き渡し  
 次の例では、参照型のパラメーター `arr` を値渡しで `Change` メソッドに渡す方法について説明します。 このパラメーターは `arr` への参照であるため、配列要素の値を変更できます。 ただし、別のメモリ位置へのパラメーターの再割り当ては、メソッドの内部でのみ機能し、元の変数 `arr` には影響しません。  
  
 [!code-csharp[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]  
  
 前の例では、`ref` パラメーターなしで参照型の配列 `arr` がメソッドに渡されています。 このような場合は、`arr` を指す参照のコピーがメソッドに渡されます。 出力は、メソッドが配列要素のコンテンツを変更できることを示しています。この場合は `1` から `888` に変更します。 ただし、`Change` メソッド内で [new](../../../csharp/language-reference/keywords/new.md) 演算子を使用して新しいメモリ領域を割り当てると、変数 `pArray` が新しい配列を参照します。 このため、この後のすべての変更が、`Main` の内部で作成される元の配列 `arr` に影響しません。 実際、この例では、2 つの配列が作成されます。1 つは `Main` の内部で、もう 1 つは `Change` メソッド内で作成されます。  
  
## <a name="passing-reference-types-by-reference"></a>参照渡しによる参照型の引き渡し  
 次の例は、前の例と同じですが、`ref` キーワードがメソッド ヘッダーと呼び出しに追加されている点が異なります。 メソッドで行われるすべての変更が、呼び出し元のプログラム内の元の変数に影響します。  
  
 [!code-csharp[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]  
  
 メソッド内で行われるすべての変更は、`Main` の元の配列に影響します。 実際、元の配列は `new` 演算子を使用して再割り当てされます。 したがって、`Change` メソッドを呼び出した後、`arr` へのすべての参照が、`Change` メソッドで作成された 5 つの要素を持つ配列を指します。  
  
## <a name="swapping-two-strings"></a>2 つの文字列のスワップ  
 文字列のスワップは、参照渡しで参照型パラメーターを渡す良い例です。 例では、2 つの文字列 `str1` と `str2` が `Main` で初期化され、`ref` キーワードで変更されたパラメーターとして `SwapStrings` メソッドに渡されます。 2 つの文字列は、メソッド内と `Main` 内でスワップされます。  
  
 [!code-csharp[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]  
  
 この例では、呼び出し元のプログラム内の変数に影響を与えるため、参照渡しでパラメーターを渡す必要があります。 メソッド ヘッダーと、メソッドの呼び出しの両方から `ref` キーワードを削除すると、呼び出し元プログラムで変更は行われません。  
  
 文字列の詳細については、「[文字列](../../../csharp/language-reference/keywords/string.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
 [パラメーターの引き渡し](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)  
 [ref と out を使用した配列の引き渡し](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)  
 [ref](../../../csharp/language-reference/keywords/ref.md)  
 [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md)  
 [out](../../../csharp/language-reference/keywords/out.md)  
 [参照型](../../../csharp/language-reference/keywords/reference-types.md)
