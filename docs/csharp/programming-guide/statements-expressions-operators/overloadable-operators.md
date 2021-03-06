---
title: "オーバーロードされた演算子 (C# プログラミング ガイド)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, operator overloading
- operator overloading [C#]
ms.assetid: 390d9d01-79fc-40ab-9ed3-0bf448da1b6a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7487f398ec412c4a302054ade20800f431e2c793
ms.sourcegitcommit: 22a48b64a0150a60b00b4fc4d8c62cde7f1670c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2018
---
# <a name="overloadable-operators-c-programming-guide"></a>オーバーロードされた演算子 (C# プログラミング ガイド)

C# では、[operator](../../../csharp/language-reference/keywords/operator.md) キーワードを使用して静的なメンバー関数を定義することで、ユーザー定義型で演算子をオーバーロードできます。 ただし、次の表に示すように、すべての演算子をオーバーロードできるわけではなく、制限付きでオーバーロードできる演算子もあります。

| 演算子 | オーバーロード可/不可 |
| --------- | --------------- |
|[+](../../../csharp/language-reference/operators/addition-operator.md)、[-](../../../csharp/language-reference/operators/subtraction-operator.md)、[!](../../../csharp/language-reference/operators/logical-negation-operator.md)、[~](../../../csharp/language-reference/operators/bitwise-complement-operator.md)、[++](../../../csharp/language-reference/operators/increment-operator.md)、[--](../../../csharp/language-reference/operators/decrement-operator.md)、[true](../../../csharp/language-reference/keywords/true.md)、[false](../../../csharp/language-reference/keywords/false.md)|これらの単項演算子はオーバーロードできます。|
|[+](../../../csharp/language-reference/operators/addition-operator.md)、[-](../../../csharp/language-reference/operators/subtraction-operator.md)、[\*](../../../csharp/language-reference/operators/multiplication-operator.md)、[/](../../../csharp/language-reference/operators/division-operator.md)、[%](../../../csharp/language-reference/operators/modulus-operator.md)、[&](../../../csharp/language-reference/operators/and-operator.md)、[&#124;](../../../csharp/language-reference/operators/or-operator.md)、[^](../../../csharp/language-reference/operators/xor-operator.md)、[\<\<](../../../csharp/language-reference/operators/left-shift-operator.md)、[>>](../../../csharp/language-reference/operators/right-shift-operator.md)|これらの 2 項演算子はオーバーロードできます。|
|[==](../../../csharp/language-reference/operators/equality-comparison-operator.md)、[!=](../../../csharp/language-reference/operators/not-equal-operator.md)、[\<](../../../csharp/language-reference/operators/less-than-operator.md)、[>](../../../csharp/language-reference/operators/greater-than-operator.md)、[\<=](../../../csharp/language-reference/operators/less-than-equal-operator.md)、[>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md)|比較演算子はオーバーロードできます (この表の後の注を参照してください)。|
|[&&](../../../csharp/language-reference/operators/conditional-and-operator.md)、[&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)|条件付き論理演算子はオーバーロードできません。ただし、オーバーロードできる `&` と <code>&#124;</code> を使用して評価できます。|
|[&#91;&#93;](../../../csharp/language-reference/operators/index-operator.md)|配列のインデックス付け演算子はオーバーロードできませんが、インデクサーを定義できます。|
|[(T)x](../../../csharp/language-reference/operators/invocation-operator.md)|キャスト演算子はオーバーロードできませんが、新しい変換演算子を定義できます (「[explicit](../../../csharp/language-reference/keywords/explicit.md)」および「[implicit](../../../csharp/language-reference/keywords/implicit.md)」を参照してください)。|
|[+=](../../../csharp/language-reference/operators/addition-assignment-operator.md), [-=](../../../csharp/language-reference/operators/subtraction-assignment-operator.md), [\*=](../../../csharp/language-reference/operators/multiplication-assignment-operator.md), [/=](../../../csharp/language-reference/operators/division-assignment-operator.md), [%=](../../../csharp/language-reference/operators/modulus-assignment-operator.md), [&=](../../../csharp/language-reference/operators/and-assignment-operator.md), [&#124;=](../../../csharp/language-reference/operators/or-assignment-operator.md), [^=](../../../csharp/language-reference/operators/xor-assignment-operator.md), [\<\<=](../../../csharp/language-reference/operators/left-shift-assignment-operator.md), [>>=](../../../csharp/language-reference/operators/right-shift-assignment-operator.md)|代入演算子はオーバーロードできません。ただし、たとえばオーバーロードできる `+` を使用して `+=` を評価することができます。|
|[=](../../../csharp/language-reference/operators/assignment-operator.md)、[.](../../../csharp/language-reference/operators/member-access-operator.md)、[?:](../../../csharp/language-reference/operators/conditional-operator.md)、[??](../../../csharp/language-reference/operators/null-conditional-operator.md)、[->](../../../csharp/language-reference/operators/dereference-operator.md)、[=>](../../../csharp/language-reference/operators/lambda-operator.md)、[f(x)](../../../csharp/language-reference/operators/invocation-operator.md)、[as](../../../csharp/language-reference/keywords/as.md)、[checked](../../../csharp/language-reference/keywords/checked.md)、[unchecked](../../../csharp/language-reference/keywords/unchecked.md)、[default](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md)、[delegate](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)、[is](../../../csharp/language-reference/keywords/is.md)、[new](../../../csharp/language-reference/keywords/new.md)、[sizeof](../../../csharp/language-reference/keywords/sizeof.md)、[typeof](../../../csharp/language-reference/keywords/typeof.md)|これらの演算子はオーバーロードできません。|

> [!NOTE]
> 比較演算子をオーバーロードする場合はペアでオーバーロードする必要があります。つまり、`==` をオーバーロードする場合は `!=` もオーバーロードする必要があります。 逆もまた真であり、`!=` をオーバーロードする場合は、`==` のオーバーロードも必要です。 比較演算子 `<` と `>`、および `<=` と `>=` の場合も同様です。

カスタム クラスの演算子をオーバーロードするには、クラスに正しい署名を持つメソッドを作成する必要があります。 メソッド名は "operator X" とする必要があります。ここで、X は、オーバーロードされる演算子の名前またはシンボルです。 単項演算子にはパラメーターが 1 つ、2 項演算子にはパラメーターが 2 つあります。 いずれの場合も、1 つのパラメーターが演算子を宣言するクラスまたは構造体と同じ型である必要があります。

```csharp
public static Complex operator +(Complex c1, Complex c2)
{
    return new Complex(c1.real + c2.real, c1.imaginary + c2.imaginary);
}
```

定義では、単純に式の結果をすぐに返すのが一般的です。  これらの状況に対しては、`=>` を使用する構文ショートカットがあります。

```csharp
public static Complex operator +(Complex c1, Complex c2) =>
        new Complex(c1.real + c2.real, c1.imaginary + c2.imaginary);
  
// Override ToString() to display a complex number in the traditional format:
public override string ToString() => $"{this.real} + {this.imaginary}";
```

詳細については、「[方法: 演算子のオーバーロードを使用して複素数クラスを作成する](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md)」を参照してください。

## <a name="see-also"></a>関連項目

[C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
[ステートメント、式、および演算子](../../../csharp/programming-guide/statements-expressions-operators/index.md)  
[演算子](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
[C# 演算子](../../../csharp/language-reference/operators/index.md)  
[C# のオーバーロードされた演算子が常に静的である理由](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/)
