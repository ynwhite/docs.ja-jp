---
title: "ICorRuntimeHost::CreateDomainEx メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorRuntimeHost.CreateDomainEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a2a577e1bd8765c7359e521b007bea943de7a984
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostcreatedomainex-method"></a>ICorRuntimeHost::CreateDomainEx メソッド
アプリケーション ドメインを作成します。 呼び出し元が、型のインターフェイス ポインターを受け取ります<xref:System._AppDomain>、型のインスタンスに<xref:System.AppDomain?displayProperty=nameWithType>です。 この方法では、呼び出し、返されたその他の機能を構成する IAppDomainSetup インスタンス<xref:System._AppDomain>インスタンス。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pwzFriendlyName`  
 [in]ドメインにわかりやすい名前を指定するために使用する省略可能なパラメーター。 このフレンドリ名は、ドメインを識別するデバッガーなどのユーザー インターフェイスで表示できます。  
  
 `pSetup`  
 [in]型の省略可能なインターフェイス ポインター`IAppDomainSetup`への呼び出しによって取得した、 [icorruntimehost::createdomainsetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)メソッドです。  
  
 `pIdentityArray`  
 [in]ポインターの省略可能な配列`IIdentity`権限セットを確立するためにセキュリティ ポリシーによってマップされている証拠を表すインスタンス。 `IIdentity`オブジェクトを取得するには呼び出すことによって、 [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)メソッドです。  
  
 `pAppDomain`  
 [out]型のインターフェイス ポインター<xref:System._AppDomain>のインスタンスに<xref:System.AppDomain?displayProperty=nameWithType>ドメインをさらに制御を使用できます。  
  
## <a name="return-value"></a>戻り値  
  
|HRESULT|説明|  
|-------------|-----------------|  
|S_OK|操作が正常に完了しました。|  
|S_FALSE|操作を完了できませんでした。|  
|E_FAIL|未知の致命的なエラーが発生しました。 メソッドには、E_FAIL が返されます、共通言語ランタイム (CLR) は、プロセスで使用可能なできなくします。 Api をホストに以降の呼び出しでは、HOST_E_CLRNOTAVAILABLE を返します。|  
|HOST_E_CLRNOTAVAILABLE|CLR が、プロセスに読み込まれていませんまたは CLR は、状態をマネージ コードを実行またはできないの呼び出しは正常に処理します。|  
  
## <a name="remarks"></a>コメント  
 `CreateDomainEx`機能を拡張[CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)を渡す、呼び出し元を許可することで、`IAppDomainSetup`アプリケーション ドメインを構成するためのプロパティ値を持つインスタンス。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** MSCorEE.h  
  
 **ライブラリ:** MSCorEE.dll にリソースとして含まれています。  
  
 **.NET framework のバージョン:** 1.0、1.1  
  
## <a name="see-also"></a>参照  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 <xref:System.IAppDomainSetup?displayProperty=nameWithType>  
 [CreateDomain メソッド](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)  
 [ICorRuntimeHost インターフェイス](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
