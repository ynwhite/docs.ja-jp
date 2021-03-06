---
title: "Windows フォームにおけるドラッグ アンド ドロップ機能"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drag and drop [Windows Forms], Windows Forms
- Windows Forms, drag and drop
ms.assetid: 65cd2c03-8782-474e-b958-cbe43eeb902c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 86234aca209c5533abf9025911b22c391b0ef22b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="drag-and-drop-functionality-in-windows-forms"></a>Windows フォームにおけるドラッグ アンド ドロップ機能
Windows フォームには、ドラッグ アンド ドロップの動作を実装する一連のメソッド、イベント、およびクラスが含まれています。 このトピックでは、Windows フォームでのドラッグ アンド ドロップのサポートの概要について説明します。  参照してください[ドラッグ アンド ドロップ操作とクリップボードのサポート](http://msdn.microsoft.com/library/fe5ebfwe\(v=vs.110\))です。  
  
## <a name="performing-drag-and-drop-operations"></a>ドラッグ アンド ドロップ操作の実行  
 ドラッグ アンド ドロップ操作を実行するには、<xref:System.Windows.Forms.Control> クラスの <xref:System.Windows.Forms.Control.DoDragDrop%2A> メソッドを使用します。 ドラッグ アンド ドロップ操作の実行方法の詳細については、「<xref:System.Windows.Forms.Control.DoDragDrop%2A>」を参照してください。 ドラッグ アンド ドロップ操作が開始される前に、マウス ポインターがドラッグされる四角形を取得するには、<xref:System.Windows.Forms.SystemInformation> クラスの <xref:System.Windows.Forms.SystemInformation.DragSize%2A> プロパティを使用します。  
  
## <a name="events-related-to-drag-and-drop-operations"></a>ドラッグ アンド ドロップ操作に関連するイベント  
 ドラッグ アンド ドロップ操作のイベントには、ドラッグ アンド ドロップ操作の現在のターゲットで発生するイベントと、ドラッグ アンド ドロップ操作のソースで発生するイベントの 2 つのカテゴリがあります。  
  
### <a name="events-on-the-current-target"></a>現在のターゲットでのイベント  
 次の表は、ドラッグ アンド ドロップ操作の現在のターゲットで発生するイベントを示します。  
  
|マウス イベント|説明|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.DragEnter>|このイベントは、オブジェクトがコントロールの境界内にドラッグされると発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.DragEventArgs> の引数を受け取ります。|  
|<xref:System.Windows.Forms.Control.DragOver>|このイベントは、マウス ポインターがコントロールの境界内にある間にオブジェクトがドラッグされるときに発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.DragEventArgs> の引数を受け取ります。|  
|<xref:System.Windows.Forms.Control.DragDrop>|このイベントは、ドラッグ アンド ドロップ操作が完了したときに発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.DragEventArgs> の引数を受け取ります。|  
|<xref:System.Windows.Forms.Control.DragLeave>|このイベントは、オブジェクトがコントロールの境界外にドラッグされたときに発生します。 このイベントのハンドラーは、型 <xref:System.EventArgs> の引数を受け取ります。|  
  
 <xref:System.Windows.Forms.DragEventArgs> クラスは、マウスのポインターの場所、マウス ボタンとキーボードの修飾子キーの現在の状態、ドラッグされているデータ、およびドラッグ イベントのソースによって許可される操作と操作に対するターゲットのドロップの効果を指定する <xref:System.Windows.Forms.DragDropEffects> の値を提供します。  
  
### <a name="events-on-the-source"></a>ソースのイベント  
 次の表は、ドラッグ アンド ドロップ操作のソースで発生するイベントを示します。  
  
|マウス イベント|説明|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.GiveFeedback>|このイベントは、ドラッグ操作中に発生します。 マウス ポインターを変更するなど、ドラッグ アンド ドロップ操作が実行されていることを示す視覚上の手掛かりをユーザーに示す機会を提供します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.GiveFeedbackEventArgs> の引数を受け取ります。|  
|<xref:System.Windows.Forms.Control.QueryContinueDrag>|このイベントは、ドラッグ アンド ドロップ操作中に発生し、ドラッグ ソースがドラッグ アンド ドロップ操作をキャンセルする必要があるかどうかを決定できるようにします。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.QueryContinueDragEventArgs> の引数を受け取ります。|  
  
 <xref:System.Windows.Forms.QueryContinueDragEventArgs> クラスは、マウス ボタンとキーボードの修飾子キーの現在の状態、ESC キーを押したかどうかを指定する値、およびドラッグ アンド ドロップ操作を続行するかどうかを指定するために設定できる <xref:System.Windows.Forms.DragAction> の値を提供します。  
  
## <a name="see-also"></a>参照  
 [Windows フォーム アプリケーションにおけるマウス入力](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
