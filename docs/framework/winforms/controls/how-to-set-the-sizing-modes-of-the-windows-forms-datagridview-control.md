---
title: "方法 : Windows フォーム DataGridView コントロールのサイズ変更モードを設定する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], setting sizing modes
- DataGridView control [Windows Forms], sizing modes
ms.assetid: e9ad15e6-b4bb-44aa-a767-3738e9db1651
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3ae9cfe338e4e9c9ecc4a1fba67164ffc4af5307
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control"></a>方法 : Windows フォーム DataGridView コントロールのサイズ変更モードを設定する
次の手順では、<xref:System.Windows.Forms.DataGridView> コントロールおよびコントロール内の特定の列に対して使用できるサイズ変更オプションをカスタマイズまたは組み合わせる一般的なシナリオを示します。  
  
### <a name="to-create-a-fixed-width-column"></a>固定幅の列を作成するには  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> プロパティを <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None> に、<xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> プロパティを <xref:System.Windows.Forms.DataGridViewTriState.False> に、<xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> プロパティを `true` に、<xref:System.Windows.Forms.DataGridViewColumn.Width%2A> プロパティに適切な値をそれぞれ設定します。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#10)]  
  
### <a name="to-create-a-column-that-adjusts-its-size-to-fit-its-content"></a>コンテンツに合わせてサイズが調整される列を作成するには  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> プロパティを、コンテンツに基づくサイズ変更モードに設定します。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#20)]  
  
### <a name="to-create-fill-mode-columns-for-values-of-varying-size-and-importance"></a>サイズと重要度が異なる値に対してフィル モードの列を作成するには  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType> プロパティを <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill> に設定し、この値をオーバーライドしないすべての列のサイズ変更モードを設定します。 列の <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> プロパティを、平均のコンテンツ幅に比例した値に設定します。 重要な列の <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> プロパティを設定して、コンテンツを部分的に表示できるようにします。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#30)]  
  
## <a name="example"></a>例  
 ここで説明したサイズ変更オプションを理解するために役立つデモ アプリケーションを次の完全なコード例に示します。  
  
 [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#00)]  
  
 このデモ アプリケーションは、次のようにして使用します。  
  
-   フォームのサイズを変更します。 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> プロパティ値で指定した比率を維持しながら、フィル モードの列の幅が変化する様子を確認します。 フォームが小さすぎる場合に、列の <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> より狭くは変更されない様子を確認します。  
  
-   マウスで列の区分線をドラッグして、列のサイズを変更します。 一部の列ではサイズ変更ができない様子、およびサイズ変更可能な列でも幅を最小幅よりも狭くできない様子を確認します。  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
-   System アセンブリおよび System.Windows.Forms アセンブリへの参照。  
  
 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] または [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] のコマンド ラインからこの例をビルドする方法については、「[コマンド ラインからのビルド](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)」または「[csc.exe を使用したコマンド ラインからのビルド](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)」を参照してください。 また、コードを新しいプロジェクトに貼り付けることにより、[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] でこの例をビルドすることもできます。  また、「 [方法: 完成した Windows フォーム コードの例を Visual Studio を使ってコンパイルして実行する](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))」も参照してください。  
  
## <a name="see-also"></a>参照  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>  
 <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A?displayProperty=nameWithType>
