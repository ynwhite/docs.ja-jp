---
title: "方法: Visual Basic で固定幅のテキスト ファイルを読み取る"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- fixed-width text file
- reading text files [Visual Basic], fixed-width
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- text files [Visual Basic], reading
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a5caa124af1bf4681a4c061f453ce5e09ec2dae7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-from-fixed-width-text-files-in-visual-basic"></a>方法: Visual Basic で固定幅のテキスト ファイルを読み取る
`TextFieldParser` オブジェクトには、構造化されたテキスト ファイル (ログなど) を簡単にかつ効率的に解析する方法が備わっています。  
  
 解析対象のファイルが区切り形式であるか固定幅フィールドであるかは、`TextFieldType` プロパティで定義します。 固定幅のテキスト ファイルでは、最終フィールドを可変幅とすることができます。 最後のフィールドを可変幅として指定するには、その幅に 0 以下の値を指定します。  
  
### <a name="to-parse-a-fixed-width-text-file"></a>固定幅のテキスト ファイルを解析するには  
  
1.  新しい `TextFieldParser` を作成します。 次のコードは、`Reader` という名前の `TextFieldParser` を作成し、`test.log` ファイルを開きます。  
  
     [!code-vb[VbFileIORead#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_1.vb)]  
  
2.  `TextFieldType` プロパティを `FixedWidth` として定義し、幅と形式を定義します。 次のコードでは、テキストの列を定義しています。先頭列の幅が 5 文字、2 列目が 10 文字、3 列目が 11 文字、そして 4 列目が可変幅です。  
  
     [!code-vb[VbFileIORead#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_2.vb)]  
  
3.  ファイル内のフィールドをループします。 破損している行が見つかった場合は、エラーを報告して解析を続行します。  
  
     [!code-vb[VbFileIORead#11](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_3.vb)]  
  
4.  `While` ブロックと `Using` ブロックをそれぞれ `End While` と `End Using` で閉じます。  
  
     [!code-vb[VbFileIORead#12](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_4.vb)]  
  
## <a name="example"></a>例  
 次のコードは、`test.log` ファイルから読み取りを行う例です。  
  
 [!code-vb[VbFileIORead#13](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_5.vb)]  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 次の条件を満たす場合は、例外が発生する可能性があります。  
  
-   指定された形式で行を解析できない (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>)。 例外の原因となった行が例外メッセージで報告され、その行に含まれているテキストには <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> プロパティが代入されます。  
  
-   指定されたファイルが存在しない (<xref:System.IO.FileNotFoundException>)。  
  
-   部分信頼の状況下で、ファイルにアクセスするために必要なアクセス許可がユーザーにない。 (<xref:System.Security.SecurityException>).  
  
-   パスが長すぎる (<xref:System.IO.PathTooLongException>)。  
  
-   ファイルにアクセスする十分なアクセス許可がユーザーにない (<xref:System.UnauthorizedAccessException>)。  
  
## <a name="see-also"></a>関連項目  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>  
 [方法: コンマ区切りのテキスト ファイルを読み取る](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)  
 [方法: 複数の書式を持つテキスト ファイルを読み取る](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)  
 [TextFieldParser オブジェクトによるテキスト ファイルの解析](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 [チュートリアル: Visual Basic によるファイルとディレクトリの操作](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 [トラブルシューティング : テキスト ファイルの読み取りと書き込み](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)  
 
