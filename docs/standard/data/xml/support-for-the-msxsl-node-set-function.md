---
title: "msxsl:node-set() 関数のサポート"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7cd79acbdef09acb0a05c818d8358cd612c3bcdf
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/23/2017
---
# <a name="support-for-the-msxslnode-set-function"></a>msxsl:node-set() 関数のサポート
`msxsl:node-set` 関数を使用すると、結果ツリー フラグメントをノード セットに変換できます。 結果として得られるノード セットには、常に単一のノードが含まれています。また、このノード セットは、常にそのツリーのルート ノードです。  
  
> [!NOTE]
>  <xref:System.Xml.Xsl.XslTransform> では、[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] クラスが廃止されています。 <xref:System.Xml.Xsl.XslCompiledTransform> クラスを使用して XSLT (Extensible Stylesheet Language for Transformations) 変換を実行できます。 詳細については、「[XslCompiledTransform クラスの使用](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)」と「[XslTransform クラスからの移行](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)」を参照してください。  
  
 `msxsl:node-set` 関数を使用すると、結果ツリー フラグメントをノード セットに変換できます。 結果として得られるノード セットには、常に単一のノードが含まれています。また、このノード セットは、常にそのツリーのルート ノードです。  
  
## <a name="example"></a>例  
 `$var` という変数がスタイル シート内のノード ツリーである例を次に示します。 for-each ステートメントを `node-set` 関数と組み合わせて使用すれば、このノード ツリーをノード セットとして反復処理できます。  
  
## <a name="nodesetxsl"></a>nodeset.xsl  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.contoso.com"  
                version="1.0">  
    <xsl:variable name="books">  
        <book author="Michael Howard">Writing Secure Code</book>  
        <book author="Michael Kay">XSLT Reference</book>  
    </xsl:variable>  
  
    <xsl:template match="/">  
        <authors>  
            <xsl:for-each select="msxsl:node-set($books)/book">   
                <author><xsl:value-of select="@author"/)</author>  
            </xsl:for-each>  
        </authors>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
## <a name="output"></a>出力  
 変換による出力は次のとおりです。  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## <a name="see-also"></a>参照  
 [XslTransform クラスによる XSLT プロセッサの実装](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
