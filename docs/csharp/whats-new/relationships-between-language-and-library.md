---
title: "言語機能とライブラリ型間のリレーションシップ | Microsoft Docs"
description: "言語機能は多くの場合、実装のためにライブラリ型に依存します。 そのリレーションシップを理解します。"
keywords: "C# 言語の設計、標準ライブラリ"
author: billwagner
ms.author: wiwagn
ms.date: 07/20/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: b7de4fdb4356e8822dba6aaaf67d615980ff09cd
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2018
---
# <a name="relationships-between-language-features-and-library-types"></a>言語機能とライブラリ型間のリレーションシップ

C# 言語の定義には、標準ライブラリに特定の型とその型にアクセス可能な特定のメンバーがある必要があります。 コンパイラは、多くの異なる言語機能に必要なこれらの型とメンバーを使用するコードを生成します。 これらの型やメンバーがまだ展開されていない環境のためのコードを記述する場合に、必要な場合には、その言語の新しいバージョンに必要な型が含まれている NuGet パッケージがあります。

この標準ライブラリ機能に対する依存関係は、C# 言語の最初のバージョンからその一部となっています。 そのバージョンでは、次の例が含まれています。

* <xref:System.Exception>: 例外を生成したすべてのコンパイラに使用されます。
* <xref:System.String>: C# `string` 型は <xref:System.String> のシノニムです。
* <xref:System.Int32>: `int` のシノニム。

その最初のバージョンは単純でした。コンパイラと標準ライブラリは共に出荷され、それぞれ 1 つのバージョンしかありませんでした。

C# の以降のバージョンでは、随時、依存関係に新しい型またはメンバーが追加されています。 例として、<xref:System.Runtime.CompilerServices.INotifyCompletion>、<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>、<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute> があります。 C# 7.0 では、<xref:System.ValueTuple> で依存関係を追加して[タプル](../tuples.md)言語機能を実装することで、これを続けています。

言語設計チームは、準拠している標準ライブラリで必要な型およびメンバーのアクセス領域を最小限に抑えることに取り組んでいます。 その目標は、新しいライブラリ機能が言語にシームレスに組み込まれているクリーン設計と両立させることです。 将来、標準ライブラリ内の新しい型とメンバーを必要とする C# の新バージョンが登場するでしょう。 自分の作業でこれらの依存関係を管理する方法を理解することが重要です。

## <a name="managing-your-dependencies"></a>依存関係の管理

C# コンパイラ ツールは現在、サポートされているプラットフォームの .NET ライブラリのリリース サイクルと切り離されています。 実際、.NET ライブラリごとに異なるリリース サイクルがあります。Windows の .NET Framework は、Windows Update としてリリースされ、.NET Core は個別のスケジュールで出荷されます。また、ライブラリの更新の Xamarin バージョンは、各ターゲット プラットフォーム用の Xamarin ツールとともに出荷されます。

ほとんどの場合、これらの変更に気付くことはありません。 ただし、そのプラットフォーム上の .NET ライブラリ内にまだない機能を必要とする言語の新しいバージョンを使用している場合は、それらの新しい型を提供する NuGet パッケージを参照することになります。
お使いのアプリがサポートしているプラットフォームが新しいフレームワークのインストールで更新されるときに、余分な参照を削除できます。

この分離は、対応するフレームワークがない可能性があるマシンを対象とする場合でも、新しい言語機能を使用できることを意味します。
