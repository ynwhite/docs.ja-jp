---
title: "&lt;serviceCertificate&gt; 要素の &lt;authentication&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;serviceCertificate&gt; 要素の &lt;authentication&gt;
SSL\/TLS ネゴシエーションを使用して取得されたサービス証明書を認証するためにクライアント プロキシが使用する設定を指定します。  
  
## 構文  
  
```  
  
<authentication customCertificateValidatorType="String" certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"   
trustedStoreLocation="LocalMachine/CurrentUser" />  
```  
  
## 属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### 属性  
  
|属性|説明|  
|--------|--------|  
|customCertificateValidatorType|文字列。  カスタム型の検証に使用される型およびアセンブリです。|  
|certificateValidationMode|資格情報の検証に使用される 3 つのモードのいずれかを指定します。  `Custom` に設定されている場合、customCertificateValidator も指定する必要があります。  既定値は、`ChainTrust` です。|  
|revocationMode|証明書失効リスト \(CRL\) のチェックに使用されるモードのいずれかです。  既定値は、`Online` です。|  
|trustedStoreLocation|2 つのシステム格納場所 \(`LocalMachine` または `CurrentUser`\) のいずれかです。  この値は、サービス証明書がクライアントにネゴシエートされるときに使用されます。  指定された格納場所の **\[信頼されたユーザー\]** ストアに対して検証が実行されます。  既定値は、`CurrentUser` です。|  
  
## customCertificateValidator 属性  
  
|値|説明|  
|-------|--------|  
|String|タイプ名およびアセンブリと、タイプの検索に使用される他のデータを指定します。|  
  
## certificateValidationMode 属性  
  
|値|説明|  
|-------|--------|  
|列挙型|None、PeerTrust、ChainTrust、PeerOrChainTrust、Custom のいずれかの値にします。<br /><br /> 詳細については、「[証明書の使用](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)」を参照してください。|  
  
## revocationMode 属性  
  
|値|説明|  
|-------|--------|  
|列挙型|NoCheck、Online、Offline のいずれかの値にします。<br /><br /> 詳細については、「[証明書の使用](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)」を参照してください。|  
  
## trustedStoreLocation 属性  
  
|値|説明|  
|-------|--------|  
|列挙型|LocalMachine または CurrentUser のいずれかの値。  既定値は CurrentUser です。  クライアント アプリケーションがシステム アカウントで実行されている場合、証明書は通常 LocalMachine の下にあります。  クライアント アプリケーションがユーザー アカウントで実行されている場合、証明書は通常 CurrentUser の下にあります。|  
  
### 子要素  
 なし。  
  
### 親要素  
  
|要素|説明|  
|--------|--------|  
|[\<serviceCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|クライアントに対してサービスを認証する際に使用される証明書を指定します。|  
  
## 解説  
 この構成要素の `certificateValidationMode` 属性は、証明書の認証に使用される信頼レベルを指定します。  既定のレベルは `ChainTrust` に設定され、チェーンの最上位の信頼された証明機関で終了する証明書の階層構造で各証明書を検索するよう指定します。  これは最もセキュリティで保護されているモードです。  また、値を `PeerOrChainTrust` に設定することもできます。これは、信頼されたチェーン内の証明書と共に、自己発行された証明書 \(ピア信頼\) も受け入れるよう指定します。  自己発行の資格情報は信頼された証明機関から購入したものである必要はないため、この値はクライアントとサービスの開発およびデバッグに使用されます。  クライアントを展開するときは、代わりに `ChainTrust` 値を使用します。  値を `Custom` または `None` に設定することもできます。  `Custom` 値を使用するには、`customCertificateValidator` 属性を証明書の検証に使用するアセンブリと型に設定することも必要です。  独自のカスタム検証を作成するには、抽象 X509CertificateValidator クラスを継承する必要があります。  詳細については、「[方法 : カスタム証明書検証を使用するサービスを作成する](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)」を参照してください。  
  
 `revocationMode` 属性は、証明書が失効していないかどうかをチェックする方法を指定します。  既定値は `online` です。この場合、証明書が失効していないかどうかを自動的にチェックします。  詳細については、「[証明書の使用](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)」を参照してください。  
  
## 使用例  
 次の例は、2 つのタスクを実行します。  最初は、ドメイン名が www.contoso.com であるエンドポイントと HTTPプロトコルを経由して通信するときに使用するクライアントのサービス証明書を指定します。  次に、認証中に使用される失効モードとストアの場所を指定します。  
  
```  
<serviceCertificate>  
  <defaultCertificate findValue="www.contoso.com"   
                      storeLocation="LocalMachine"  
                      storeName="TrustedPeople"   
                      x509FindType="FindByIssuerDistinguishedName" />  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
  <authentication revocationMode="Online"   
   trustedStoreLocation="LocalMachine" />  
</serviceCertificate>  
```  
  
## 参照  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>   
 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>   
 [セキュリティ動作](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [証明書の使用](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [方法 : カスタム証明書検証を使用するサービスを作成する](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)   
 [\<authentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)   
 [クライアントのセキュリティ保護](../../../../../docs/framework/wcf/securing-clients.md)   
 [サービスおよびクライアントのセキュリティ保護](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)