---
title: コマンド ラインからのビルド (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c3f71a84feffce46bafd92ff701a0250c059a82e
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="building-from-the-command-line-visual-basic"></a>コマンド ラインからのビルド (Visual Basic)
A[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]プロジェクトで構成される 1 つまたは複数の独立したソース ファイルです。 コンパイルと呼ばれる過程で、これらのファイルが 1 つのパッケージにまとめられて — アプリケーションとして実行できる 1 つの実行可能ファイルです。  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 内からプログラムをコンパイルする代わりに、コマンド ライン コンパイラを提供、[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]統合開発環境 (IDE) です。 コマンド ライン コンパイラが状況を必要としない、IDE の機能の完全なセット用に設計された — たとえば、またはする場合を使用して限られたシステムのメモリまたはストレージの領域を持つコンピューター用の記述。  
  
  内からソース ファイルをコンパイルする、 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] IDE、選択、**ビルド**コマンドを**ビルド**メニュー。  
  
> [!TIP]
>  関連付けられているに関する情報を表示するには、Visual Studio IDE を使用してプロジェクト ファイルをビルドするときに**vbc**コマンドと、出力ウィンドウにそのスイッチ。 この情報を表示、開く、[オプション ダイアログ ボックス、プロジェクトとソリューションをビルドおよび実行](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)、し、設定、 **MSBuild プロジェクトのビルド出力の詳細度**に**標準**またはより高度な詳細度。 詳細については、「[方法: ビルド ログ ファイルを表示、保存、および構成する](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7)」をご覧ください。  
  
 MSBuild を使用して、コマンド プロンプトでのプロジェクト (.vbproj) ファイルをコンパイルすることができます。 詳細については、次を参照してください。[コマンド ライン リファレンス](/visualstudio/msbuild/msbuild-command-line-reference)と[チュートリアル: MSBuild を使用して](/visualstudio/msbuild/walkthrough-using-msbuild)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法 : コマンド ライン コンパイラを起動する](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 MS-DOS のプロンプトで、または特定のサブディレクトリからコマンド ライン コンパイラを起動する方法について説明します。  
  
 [コンパイル コマンド ラインのサンプル](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 独自の用途を変更するコマンドラインのサンプルの一覧を示します。  
  
## <a name="related-sections"></a>関連項目  
 [Visual Basic のコマンド ライン コンパイラ](../../../visual-basic/reference/command-line-compiler/index.md)  
 アルファベット順または目的別に整理コンパイラ オプションの一覧を提供します。  
  
 [条件付きコンパイル](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 コードの特定のセクションをコンパイルする方法について説明します。  
  
 [Visual Studio でのプロジェクトとソリューションのビルドおよびクリーン](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 対象が別のビルドに含まれます、プロジェクトのプロパティ を選択およびが正しい順序でプロジェクトのビルドを整理する方法について説明します。
