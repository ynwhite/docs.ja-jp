---
title: "方法 :テクスチャを使用して塗りつぶした直線を描画する"
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
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0aaba7981dc68bf7bdfe6dbd45685e61f7b763a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a>方法 :テクスチャを使用して塗りつぶした直線を描画する
純色で直線を描画するには、代わりに、テクスチャを使用して行を描画できます。 直線と曲線テクスチャを使用して描画するには、作成、<xref:System.Drawing.TextureBrush>オブジェクト、およびを渡す<xref:System.Drawing.TextureBrush>オブジェクトを<xref:System.Drawing.Pen.%23ctor%2A>コンス トラクターです。 テクスチャ ブラシに関連付けられたビットマップは平面 (表示)、並べて表示に使用され、ペンのストロークのテクスチャを並べて表示される特定のピクセルが明らかになったペンでは、直線または曲線が描画されるときにします。  
  
## <a name="example"></a>例  
 次の例を作成、<xref:System.Drawing.Bitmap>ファイルからオブジェクト`Texture1.jpg`です。 そのビットマップが構築するために使用される、<xref:System.Drawing.TextureBrush>オブジェクト、および<xref:System.Drawing.TextureBrush>オブジェクトを構築するために使用、<xref:System.Drawing.Pen>オブジェクト。 呼び出し<xref:System.Drawing.Graphics.DrawImage%2A>で左上隅をビットマップを描画 (0, 0) です。 呼び出し<xref:System.Drawing.Graphics.DrawEllipse%2A>を使用して、<xref:System.Drawing.Pen>テクスチャ楕円を描画するオブジェクト。  
  
 次の図は、ビットマップ、テクスチャの楕円を示します。  
  
 ![ペン](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 Windows フォームを作成し、処理、フォームの<xref:System.Windows.Forms.Control.Paint>イベント。 上記のコードを貼り付け、<xref:System.Windows.Forms.Control.Paint>イベント ハンドラー。 置き換える`Texture.jpg`イメージ システム上で有効にします。  
  
## <a name="see-also"></a>参照  
 [ペンを使用した直線と図形の描画](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Windows フォームにおけるグラフィックスと描画](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
