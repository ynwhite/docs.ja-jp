---
title: "ICorDebugType2::GetTypeID メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d18aa8210ea90736c0757e2587aab4ff143dcdad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtype2gettypeid-method"></a>ICorDebugType2::GetTypeID メソッド
取得、 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)この型にします。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `id`  
 [out]ポインター、 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)この ICorDebugType 用です。  
  
## <a name="return-value"></a>戻り値  
 戻り値は、成功の場合は `S_OK` で、失敗の場合は `HRESULT` コードです。 `HRESULT`コード、次のとおりです。  
  
|リターン コード|説明|  
|-----------------|-----------------|  
|`S_OK`|メソッドが成功しました。 メソッドは、有効なが取得[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)です。|  
|`CORDBG_E_CLASS_NOT_LOADED`|型が読み込まれていません。|  
|`CORDBG_E_UNSUPPORTED`|種類はサポートされていません。|  
  
## <a name="remarks"></a>コメント  
 このメソッドでは、マッピングを提供する可能性がありますいないに読み込まれている、実行時に、型を表す、ICorDebugType から、 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)ランタイムに読み込まれた型を識別する非透過的なとして機能する処理です。  
  
 ときに、ICorDebugType を表す型がまだ読み込まれて、このメソッドが戻る`CORDBG_E_CLASS_NOT_LOADED`です。  返すかどうか、型はサポートされていません、`CORDBG_E_UNSUPPORTED`です。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [ICorDebugType2 インターフェイス](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
