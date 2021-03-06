---
title: "ICorDebugNativeFrame2::GetStackParameterSize メソッド"
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
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fa7e67c252f2ece16c072e22d0333e085fbc4f65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a>ICorDebugNativeFrame2::GetStackParameterSize メソッド
X86 オペレーティング システム上のスタック上には、パラメーターの合計サイズを返します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pSize`  
 [out]スタックのパラメーターの合計サイズへのポインター。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。  
  
|HRESULT|説明|  
|-------------|-----------------|  
|S_OK|スタック サイズが正常に返されます。|  
|S_FALSE|`GetStackParameterSize`x86 以外のプラットフォームで呼び出されました。|  
|E_FAIL|`The size of the parameters could not be returned`。|  
|E_INVALIDARG|`pSize``null`します。|  
  
## <a name="exceptions"></a>例外  
  
## <a name="remarks"></a>コメント  
 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)メソッドは、スタックにプッシュされるパラメーターのスタック ポインターを調整できません。 によって返される値を使用する代わりに、`GetStackParameterSize`をシードするネイティブなアンワインダーは、パラメーターの調整は、スタック ポインターを調整します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [ICorDebugNativeFrame2 インターフェイス](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [デバッグ インターフェイス](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [デバッグ](../../../../docs/framework/unmanaged-api/debugging/index.md)
