---
title: "TextBox コントロールの概要 (Windows フォーム)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d7312246c43157ca9cd6c7b41d2b110586721c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="textbox-control-overview-windows-forms"></a>TextBox コントロールの概要 (Windows フォーム)
Windows フォームのテキスト ボックスは、ユーザーからの入力を取得またはテキストの表示に使用されます。 <xref:System.Windows.Forms.TextBox>コントロールもにできる読み取り専用ですが、一般に編集可能なテキストは、使用できます。 テキスト ボックスでは、複数の行を表示、コントロールのサイズにテキストを折り返す、および基本的な書式を追加することができます。 <xref:System.Windows.Forms.TextBox>コントロールが表示またはコントロールに入力されたテキストに対して単一の書式スタイルを提供します。 表示するには複数の書式設定されたテキストの種類を使用して、<xref:System.Windows.Forms.RichTextBox>コントロール。 詳細については、次を参照してください。 [RichTextBox コントロールの概要](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md)です。  
  
## <a name="working-with-the-textbox-control"></a>TextBox コントロールの操作  
 コントロールによって表示されるテキストに含まれている、<xref:System.Windows.Forms.TextBox.Text%2A>プロパティです。 既定では、最大 2048 文字のテキスト ボックスに入力できます。 設定した場合、<xref:System.Windows.Forms.TextBox.Multiline%2A>プロパティを`true`、最大 32 KB のテキストを入力することができます。 <xref:System.Windows.Forms.TextBox.Text%2A>デザイン時のプロパティ ウィンドウで、実行時コード、またはユーザーの入力によって実行時にプロパティを設定することができます。 テキスト ボックスの現在の内容は、読み取りを実行時に取得できる、<xref:System.Windows.Forms.TextBox.Text%2A>プロパティです。  
  
 次のコード例は、実行時に、コントロール内のテキストを設定します。 `InitializeMyControl`プロシージャが自動的に実行されません。 呼び出す必要があります。  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a>参照  
 <xref:System.Windows.Forms.TextBox>  
 [方法: Windows フォーム TextBox コントロールでのカーソル位置を制御する](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [方法: Windows フォームの TextBox コントロールを使用してパスワード テキスト ボックスを作成する](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [方法: 読み取り専用テキスト ボックスを作成する](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [方法: 文字列に引用符を挿入する](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [方法: Windows フォーム TextBox コントロールでテキストを選択する](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [方法: Windows フォーム TextBox コントロールで複数行を表示する](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox コントロール](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
