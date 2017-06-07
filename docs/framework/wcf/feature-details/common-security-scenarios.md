---
title: "一般的なセキュリティ シナリオ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "セキュリティ [WCF], シナリオ"
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
caps.latest.revision: 18
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 18
---
# 一般的なセキュリティ シナリオ
ここでは、考えられるさまざまなクライアントおよびサービスのセキュリティ構成の一覧を示します。構成はさまざまな要因により異なります。たとえば、サービスやクライアントがイントラネット上にあるかどうか、また、セキュリティが Windows とトランスポート \(HTTPS など\) のどちらで提供されるかなどが考えられます。  
  
## このセクションの内容  
 [セキュリティで保護されていないインターネット環境のクライアントとサービス](../../../../docs/framework/wcf/feature-details/internet-unsecured-client-and-service.md)  
 セキュリティで保護されていないパブリックなクライアントとサービスの例です。  
  
 [セキュリティで保護されていないイントラネットのクライアントとサービス](../../../../docs/framework/wcf/feature-details/intranet-unsecured-client-and-service.md)  
 セキュリティで保護されたプライベートなネットワーク上で [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] アプリケーションに情報を提供するために開発された基本的な [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] サービスです。  
  
 [基本認証でのトランスポート セキュリティ](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 アプリケーションは、カスタム認証を使用して、クライアントにログオンを許可します。  
  
 [トランスポート セキュリティと Windows 認証](../../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)  
 Windows セキュリティによってセキュリティ保護されたクライアントとサービスを示します。  
  
 [トランスポート セキュリティと匿名クライアント](../../../../docs/framework/wcf/feature-details/transport-security-with-an-anonymous-client.md)  
 このシナリオでは HTTPS などのようなトランスポート セキュリティを使用して、機密性と整合性を強化します。  
  
 [トランスポート セキュリティと証明書認証](../../../../docs/framework/wcf/feature-details/transport-security-with-certificate-authentication.md)  
 証明書によってセキュリティ保護されたクライアントとサービスを示します。  
  
 [メッセージ セキュリティと匿名クライアント](../../../../docs/framework/wcf/feature-details/message-security-with-an-anonymous-client.md)  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] メッセージ セキュリティによってセキュリティ保護されたクライアントとサービスを示します。  
  
 [ユーザー名クライアントを使用したメッセージ セキュリティ](../../../../docs/framework/wcf/feature-details/message-security-with-a-user-name-client.md)  
 クライアントは、ドメイン ユーザー名とパスワードを使用してクライアントのログオンを許可する Windows フォーム アプリケーションです。  
  
 [メッセージ セキュリティと証明書クライアント](../../../../docs/framework/wcf/feature-details/message-security-with-a-certificate-client.md)  
 サーバー側の証明書は複数あり、クライアント側の証明書はそれぞれ 1 つです。セキュリティのコンテキストは、トランスポート層セキュリティ \(TLS: Transport Layer Security\) ネゴシエーションを介して確立されます。  
  
 [Windows クライアントとのメッセージ セキュリティ](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)  
 証明書クライアントのバリエーションの 1 つです。サーバー側の証明書は複数あり、クライアント側の証明書はそれぞれ 1 つです。セキュリティのコンテキストは TLS ネゴシエーションを介して確立されます。  
  
 [資格情報ネゴシエーションを使用しない Windows クライアントを使用するメッセージ セキュリティ](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client-without-credential-negotiation.md)  
 Kerberos ドメインによってセキュリティ保護されたクライアントとサービスを示します。  
  
 [メッセージ セキュリティと相互の証明書](../../../../docs/framework/wcf/feature-details/message-security-with-mutual-certificates.md)  
 サーバー側の証明書は複数あり、クライアント側の証明書はそれぞれ 1 つです。サーバーの証明書はアプリケーションと共に配布され、帯域外でも使用可能です。  
  
 [発行済みトークンを使用したメッセージ セキュリティ](../../../../docs/framework/wcf/feature-details/message-security-with-issued-tokens.md)  
 フェデレーション セキュリティにより独立したドメイン間で信頼を確立できます。  
  
 [信頼できるサブシステム](../../../../docs/framework/wcf/feature-details/trusted-subsystem.md)  
 クライアントは、ネットワーク全体に分散している 1 つ以上の Web サービスにアクセスします。Web サービスは、セキュリティで保護する必要がある追加のリソース \(データベースや他の Web サービスなど\) にアクセスします。  
  
## 関連項目  
 <xref:System.ServiceModel>  
  
## 関連項目  
 [承認](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [セキュリティの概要](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
 [セキュリティ](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [バインディングとセキュリティ](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [サービスおよびクライアントのセキュリティ保護](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
 [認証](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [承認](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [フェデレーションと発行済みトークン](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [監査](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
## 参照  
 [セキュリティ ガイドラインとベスト プラクティス](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)   
 [Windows Server AppFabric のセキュリティ モデル](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)