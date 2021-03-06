---
title: "AssemblyComparisonResult 列挙型"
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
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2c38561a804a331df102a600d4b0b0f6312aaa6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult 列挙型
によって決定される 2 つのアセンブリ id の等価性を示す、 [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)関数。  
  
## <a name="syntax"></a>構文  
  
```  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,   
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,    
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,      
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,    
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion    
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー名|説明|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|すべてのアセンブリがフィールド比較一致していることを示します。|  
|`ACR_EquivalentFXUnified`|あるアセンブリ同等と見なされる、共通言語ランタイム (CLR) のバージョンの統一の .NET Framework version 2.0 でアセンブリのバージョン番号に基づくことを示します。|  
|`ACR_EquivalentPartialFXUnified`|.NET Framework 2.0 のアセンブリのバージョン番号の CLR 統合に対応するアセンブリは部分的に一致することを示します。|  
|`ACR_EquivalentPartialMatch`|アセンブリは部分的に一致することを示します。|  
|`ACR_EquivalentPartialUnified`|バージョン番号の従来の統一に基づいてアセンブリの部分的に一致することを示します。|  
|`ACR_EquivalentPartialWeakNamed`|単純な名前のアセンブリは部分的に一致することを示します。|  
|`ACR_EquivalentUnified`|あるアセンブリ同等と見なされる従来のバージョンの .NET Framework のバージョン番号の CLR 統合に基づくことを示します。|  
|`ACR_EquivalentWeakNamed`|一致する 2 つの単に名前付きアセンブリのバージョン番号が無視されたことを示します。|  
|`ACR_NonEquivalent`|2 つのアセンブリ間の一致が発生しなかったことを示します。|  
|`ACR_NonEquivalentPartialVersion`|2 つのアセンブリが、そのバージョン番号、部分的に一致を除くと一致することを示します。|  
|`ACR_NonEquivalentVersion`|2 つのアセンブリが一致を除き、バージョン番号、一致していないことを示します。|  
|`ACR_Unknown`|不一致の理由が不明であることを示します。|  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** Fusion.h  
  
 **ライブラリ:** MsCorEE.dll にリソースとして含まれています。  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [CompareAssemblyIdentity 関数](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 [Fusion 列挙型](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
