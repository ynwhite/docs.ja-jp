---
title: "IAssemblyName インターフェイス"
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
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 902ad9f67d06306e79666f0e10d85bdb9c65c377
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblyname-interface"></a>IAssemblyName インターフェイス
記述するおよびアセンブリの一意の id を使用するメソッドを提供します。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[Clone メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|これのシャロー コピーを作成`IAssemblyName`オブジェクト。|  
|[Finalize メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|これにより、`IAssemblyName`オブジェクト リソースを解放し、そのデストラクターが呼び出される前に、他のクリーンアップ操作を実行します。|  
|[GetDisplayName メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|これによって参照されるアセンブリの人間が判読できる名前を取得`IAssemblyName`オブジェクト。|  
|[GetName メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|これによって参照されるアセンブリの単純な暗号化されていない名前を取得`IAssemblyName`オブジェクト。|  
|[GetProperty メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|指定したによって参照されるプロパティへのポインターを取得`PropertyId`です。|  
|[GetVersion メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|これによって参照されるアセンブリのバージョン情報を取得`IAssemblyName`オブジェクト。|  
|[IsEqual メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|指定したかどうかを決定`IAssemblyName`オブジェクトがこの`IAssemblyName`指定した比較フラグに基づいて、します。|  
|[SetProperty メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|指定したによって参照されるプロパティの値を設定`PropertyId`です。|  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** Fusion.h  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [Fusion インターフェイス](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IAssemblyEnum インターフェイス](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
