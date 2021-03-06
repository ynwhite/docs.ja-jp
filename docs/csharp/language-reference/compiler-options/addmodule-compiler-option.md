---
title: "-addmodule (C# コンパイラ オプション)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: db440b58862e372e443c9c51961b0c3cc2dd211e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2018
---
# <a name="-addmodule-c-compiler-options"></a>-addmodule (C# コンパイラ オプション)
このオプションを使用すると、スイッチで作成されたモジュールが現在のコンパイルに追加されます。  
  
## <a name="syntax"></a>構文  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a>引数  
 `file`, `file2`  
 メタデータを含む出力ファイル。 このファイルには、アセンブリ マニフェストを含めることができません。 複数のファイルをインポートするには、コンマかセミコロンでファイル名を区切ります。  
  
## <a name="remarks"></a>コメント  
 **-addmodule** で追加したモジュールはすべて、実行時に出力ファイルと同じディレクトリに置かれている必要があります。 つまり、コンパイル時にはあるゆるディレクトリのモジュールを指定できますが、そのモジュールは実行時にアプリケーション ディレクトリに置かれている必要があります。 実行時にモジュールがアプリケーション ディレクトリにない場合、<xref:System.TypeLoadException> が生成されます。  
  
 `file` には、アセンブリを含めることができません。 たとえば、出力ファイルが [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) で作成された場合、そのメタデータは **-addmodule** でインポートできます。  
  
 出力ファイルが **-target:module** ではなく **-target** オプションで作成された場合、そのメタデータは **-addmodule** ではインポートできませんが、[-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) でインポートできます。  
  
 このコンパイラ オプションは Visual Studio では利用できません。プロジェクトはモジュールを参照できません。 また、このコンパイラ オプションをプログラムで変更することはできません。  
  
## <a name="example"></a>例  
 ソース ファイル `input.cs` をコンパイルし、`metad1.netmodule` と `metad2.netmodule` からメタデータを追加し、`out.exe` を生成します。  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a>参照  
 [C# コンパイラ オプション](../../../csharp/language-reference/compiler-options/index.md)  
 [プロジェクトおよびソリューションのプロパティの管理](/visualstudio/ide/managing-project-and-solution-properties)  
 [マルチファイル アセンブリ](../../../framework/app-domains/multifile-assemblies.md)  
 [方法: マルチファイル アセンブリをビルドする](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
