---
title: "CorDebugUnmappedStop 列挙型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugUnmappedStop
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugUnmappedStop
helpviewer_keywords: CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e75c827533a921c4cab31b2e8b0996dffa532fe2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="d30f6-102">CorDebugUnmappedStop 列挙型</span><span class="sxs-lookup"><span data-stu-id="d30f6-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="d30f6-103">ステッパによるコード実行の停止をトリガーする可能性のあるマップ解除したコードの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="d30f6-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d30f6-104">構文</span><span class="sxs-lookup"><span data-stu-id="d30f6-104">Syntax</span></span>  
  
```  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a><span data-ttu-id="d30f6-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d30f6-105">Members</span></span>  
  
|<span data-ttu-id="d30f6-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d30f6-106">Member</span></span>|<span data-ttu-id="d30f6-107">説明</span><span class="sxs-lookup"><span data-stu-id="d30f6-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="d30f6-108">マップされていないコードの種類では停止されません。</span><span class="sxs-lookup"><span data-stu-id="d30f6-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="d30f6-109">プロローグ コードで停止します。</span><span class="sxs-lookup"><span data-stu-id="d30f6-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="d30f6-110">エピローグ コードで停止します。</span><span class="sxs-lookup"><span data-stu-id="d30f6-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="d30f6-111">マッピング情報のないコードで停止します。</span><span class="sxs-lookup"><span data-stu-id="d30f6-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="d30f6-112">プロローグ、エピローグ、いいえ-マッピング情報、またはアンマネージ カテゴリに入らないマップされていないコードで停止します。</span><span class="sxs-lookup"><span data-stu-id="d30f6-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="d30f6-113">アンマネージ コードで停止します。</span><span class="sxs-lookup"><span data-stu-id="d30f6-113">Stop in unmanaged code.</span></span> <span data-ttu-id="d30f6-114">この値は、相互運用機能デバッグでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="d30f6-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="d30f6-115">すべての種類のマップされていないコードで停止します。</span><span class="sxs-lookup"><span data-stu-id="d30f6-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d30f6-116">コメント</span><span class="sxs-lookup"><span data-stu-id="d30f6-116">Remarks</span></span>  
 <span data-ttu-id="d30f6-117">使用して、 [icordebugstepper::setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)ステッパは停止する、マップ解除したコードを指定するフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="d30f6-117">Use the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d30f6-118">要件</span><span class="sxs-lookup"><span data-stu-id="d30f6-118">Requirements</span></span>  
 <span data-ttu-id="d30f6-119">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="d30f6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d30f6-120">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d30f6-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d30f6-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d30f6-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d30f6-122">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d30f6-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d30f6-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="d30f6-123">See Also</span></span>  
 [<span data-ttu-id="d30f6-124">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="d30f6-124">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)