---
title: "ICorDebugCode::GetILToNativeMapping メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetILToNativeMapping
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 54937e8d5d7a2e345ebcbccadbc592b12e3ee9b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="cb3ae-102">ICorDebugCode::GetILToNativeMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="cb3ae-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="cb3ae-103">Microsoft intermediate language (MSIL) オフセットからネイティブ オフセットへのマッピングを表す"COR_DEBUG_IL_TO_NATIVE_MAP"インスタンスの配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="cb3ae-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb3ae-104">構文</span><span class="sxs-lookup"><span data-stu-id="cb3ae-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb3ae-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cb3ae-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="cb3ae-106">[in] `map` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="cb3ae-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="cb3ae-107">[out]実際に返される要素の数へのポインター、`map`配列。</span><span class="sxs-lookup"><span data-stu-id="cb3ae-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="cb3ae-108">[out]配列`COR_DEBUG_IL_TO_NATIVE_MAP`以下構造、MSIL のオフセットからネイティブ オフセットへのマッピングを表します。</span><span class="sxs-lookup"><span data-stu-id="cb3ae-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` stuctures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="cb3ae-109">返される要素の配列に順序がありません。</span><span class="sxs-lookup"><span data-stu-id="cb3ae-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb3ae-110">コメント</span><span class="sxs-lookup"><span data-stu-id="cb3ae-110">Remarks</span></span>  
 <span data-ttu-id="cb3ae-111">`GetILToNativeMapping`メソッドは、この"ICorDebugCode"インスタンスがジャストでタイム (JIT) MSIL コードをコンパイルしたネイティブ コードを表す場合にのみ、意味のある結果を返します。</span><span class="sxs-lookup"><span data-stu-id="cb3ae-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb3ae-112">要件</span><span class="sxs-lookup"><span data-stu-id="cb3ae-112">Requirements</span></span>  
 <span data-ttu-id="cb3ae-113">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="cb3ae-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb3ae-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb3ae-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb3ae-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb3ae-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb3ae-116">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb3ae-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb3ae-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb3ae-117">See Also</span></span>  
 [<span data-ttu-id="cb3ae-118">ICorDebugCode Interface1</span><span class="sxs-lookup"><span data-stu-id="cb3ae-118">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)