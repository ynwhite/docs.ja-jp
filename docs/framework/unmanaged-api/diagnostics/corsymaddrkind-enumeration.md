---
title: "CorSymAddrKind 列挙体"
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
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 300913f9ea89044e425f9f05856d13fa15cdc015
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="corsymaddrkind-enumeration"></a>CorSymAddrKind 列挙体
メモリ アドレスの種類を示します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|Microsoft intermediate language (MSIL) ローカル変数またはパラメーター インデックスを示します。|  
|`ADDR_NATIVE_RVA`|モジュールへの相対仮想アドレスを示します。|  
|`ADDR_NATIVE_REGISTER`|CPU レジスタを示します。|  
|`ADDR_NATIVE_REGREL`|最初のアドレスは、レジスタと 2 番目のアドレスは、オフセットを示します。|  
|`ADDR_NATIVE_OFFSET`|ベース アドレスからのオフセットを示します。|  
|`ADDR_NATIVE_REGREG`|最初のアドレスは、レジスタの低部、2 つ目は高い部分を示します。|  
|`ADDR_NATIVE_REGSTK`|ことを示します最初のアドレスは、レジスタの不足部分であり、2 つ目は、高の部分では、3 番目のオフセット。|  
|`ADDR_NATIVE_STKREG`|最初のアドレスは、レジスタ、2 番目のオフセット、そのが、3 番目のレジスタの高い部分を示します。|  
|`ADDR_BITFIELD`|最初のアドレスは、フィールドの開始、2 番目のアドレスは、フィールド長を示します。|  
|`ADDR_NATIVE_ISECTOFFSET`|最初のアドレスは、セクションと 2 番目のアドレスは、オフセットを示します。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** CorSym.idl、CorSym.h  
  
## <a name="see-also"></a>参照  
 [シンボル ストア診断列挙型](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
