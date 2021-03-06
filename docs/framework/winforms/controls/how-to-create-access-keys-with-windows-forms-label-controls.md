---
title: "方法 : Windows フォームの Label コントロールでアクセス キーを作成する"
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
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a856090a76f484c21c1d9982d67e9fdf21e8451
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>方法 : Windows フォームの Label コントロールでアクセス キーを作成する
Windows フォーム<xref:System.Windows.Forms.Label>を他のコントロールのアクセス キーを定義するコントロールを使用できます。 ラベル コントロールにアクセス キーを定義するときに、ユーザーは ALT キーとそれに続くタブ オーダーでコントロールにフォーカスを移動するように指定した文字キーを押すことができます。 ラベルは、フォーカスを受け取ることはできません、ため、タブ オーダーの次のコントロールにフォーカスが自動的に移動します。 この手法を使用して、テキスト ボックス、コンボ ボックス、リスト ボックス、およびデータ グリッドにアクセス キーを割り当てます。  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>ラベルを持つコントロールにアクセス キーを割り当てる  
  
1.  最初に、ラベルを描画し、その他のコントロールを描画します。  
  
     - または -  
  
     任意の順序で、コントロールを描画し、設定、<xref:System.Windows.Forms.Control.TabIndex%2A>他のコントロールより 1 小さい値をラベルのプロパティです。  
  
2.  ラベルの設定<xref:System.Windows.Forms.Label.UseMnemonic%2A>プロパティを`true`です。  
  
3.  アンパサンドを使用して、ラベルのでは、(&)<xref:System.Windows.Forms.Label.Text%2A>ラベルのアクセス キーを割り当てるプロパティをします。 詳細については、次を参照してください。[アクセス キーの Windows フォーム コントロールの作成](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)です。  
  
    > [!NOTE]
    >  アクセス キーの作成に使用するのではなく、ラベル コントロールにアンパサンドを表示することがあります。 これは、アンパサンドがデータに含まれるレコード セット内のフィールドに、ラベル コントロールをバインドする場合に発生する可能性があります。 ラベル コントロールでは、アンパサンドを表示するには、設定、<xref:System.Windows.Forms.Label.UseMnemonic%2A>プロパティを`false`です。 アンパサンドを表示しても、アクセス キーを持っている場合は、設定、<xref:System.Windows.Forms.Label.UseMnemonic%2A>プロパティを`true`を示し、1 つのアンパサンドとアクセス キー (&)、アンパサンドは、2 つのアンパサンドで表示します。  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a>参照  
 [方法: Windows フォーム Label コントロールのサイズを内容に合わせて変更する](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 [Label コントロールの概要](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [Label コントロール](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
