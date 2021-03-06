---
title: "IValidator::Validate メソッド"
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
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a74249cb806f332b3ae575223f237438da616972
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ivalidatorvalidate-method"></a>IValidator::Validate メソッド
指定したポータブル実行可能 (PE) または Microsoft intermediate language (MSIL) ファイルを検証します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `veh`  
 [in]ポインター、`IVEHandler`妥当性確認エラーを処理するインスタンス。  
  
 `pAppDomain`  
 [in]ファイルが読み込まれているアプリケーション ドメインへのポインター。  
  
 `ulFlags`  
 [in]ビットごとの組み合わせ[ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md)を実行するか、検証を示す値。  
  
 `ulMaxError`  
 [in]検証を終了する前に許可されるエラーの最大数。  
  
 `token`  
 [in]使用しません。  
  
 `fileName`  
 [in]検証に使用するファイルの名前を指定する文字列。  
  
 `pe`  
 [in]ファイルが格納されているメモリ バッファーへのポインター。  
  
 `ulSize`  
 [in]検証に使用するファイルのバイト単位のサイズ。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** IValidator.idl、IValidator.h  
  
 **ライブラリ:** MSCorEE.dll にリソースとして含まれています。  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>参照  
 
