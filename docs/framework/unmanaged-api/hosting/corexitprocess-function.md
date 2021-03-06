---
title: "CorExitProcess 関数"
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
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 560f63c131ad336a3ff4b4edec0aed2b58d33ba5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="corexitprocess-function"></a>CorExitProcess 関数
現在のアンマネージ プロセスを終了します。  
  
 この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では推奨されていません。 使用して、 [iclrmetahost::exitprocess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)メソッド代わりにします。  
  
## <a name="syntax"></a>構文  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `exitCode`  
 プロセス終了コードを指定する整数。  
  
## <a name="remarks"></a>コメント  
  
> [!NOTE]
>  以降で、 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]、`CorExitProcess`すべて開始のランタイム プロセスでは、従来の Api がバインドされただけでなく、ランタイムが終了します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** MSCorEE.h  
  
 **ライブラリ:** MSCorEE.dll  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [サポートされなくなった CLR ホスト関数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
