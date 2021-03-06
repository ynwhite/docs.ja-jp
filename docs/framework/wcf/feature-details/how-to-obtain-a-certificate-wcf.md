---
title: "方法 : 証明書 (WCF) を取得する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5dcefa658aec37b9af3c4f9285ec76a0d549b868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-obtain-a-certificate-wcf"></a>方法 : 証明書 (WCF) を取得する
X.509 証明書を使用する [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] の機能を使用するには、最初に証明書を取得します。  
  
### <a name="to-obtain-an-x509-certificate"></a>X.509 証明書を取得するには  
  
1.  次のいずれかを選択します。  
  
    -   VeriSign, Inc. などの証明機関から証明書を購入します。  
  
    -   独自の証明書サービスを設定し、証明機関に証明書への署名を依頼します。 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]、Windows 2000 Server、Windows 2000 Server Datacenter、および Windows 2000 Datacenter Server にはすべて、公開キー基盤 (PKI) をサポートする証明書サービスが用意されています。 Windows Server 2008 を使用して、 [Active Directory Certificate Services](http://go.microsoft.com/fwlink/?LinkID=153483)証明機関を管理するロール。  
  
    -   独自の証明書サービスを設定し、証明書には署名しません。  
  
    > [!NOTE]
    >  どの方法を使用する場合でも、X.509 証明書を含む SOAP 要求の受信者は、その X.509 証明書を信頼する必要があります。 つまり、証明書チェーン内の X.509 証明書または発行者は、信頼されたユーザーの証明書ストア内に存在し、また X.509 証明書は信頼されない証明書ストア内には存在しないということを意味します。  
  
## <a name="see-also"></a>参照  
 [証明書の使用](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [方法 : 開発中に使用する一時的な証明書を作成する](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
