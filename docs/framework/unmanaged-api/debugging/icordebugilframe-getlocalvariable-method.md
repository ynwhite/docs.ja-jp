---
title: "ICorDebugILFrame::GetLocalVariable メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.GetLocalVariable
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 24b4ed62c3fb68306683d2199f901ec510f0da6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="c9cdf-102">ICorDebugILFrame::GetLocalVariable メソッド</span><span class="sxs-lookup"><span data-stu-id="c9cdf-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="c9cdf-103">この Microsoft intermediate language (MSIL) のスタック フレーム内には、指定されたローカル変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="c9cdf-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9cdf-104">構文</span><span class="sxs-lookup"><span data-stu-id="c9cdf-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9cdf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9cdf-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="c9cdf-106">[in]MSIL のこのスタック フレーム内のローカル変数のインデックス。</span><span class="sxs-lookup"><span data-stu-id="c9cdf-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="c9cdf-107">[out]取得した値を表す ICorDebugValue オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c9cdf-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9cdf-108">コメント</span><span class="sxs-lookup"><span data-stu-id="c9cdf-108">Remarks</span></span>  
 <span data-ttu-id="c9cdf-109">`GetLocalVariable` ・ イン タイム (JIT) コンパイル フレームまたは MSIL スタック フレームで、メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9cdf-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9cdf-110">要件</span><span class="sxs-lookup"><span data-stu-id="c9cdf-110">Requirements</span></span>  
 <span data-ttu-id="c9cdf-111">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="c9cdf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9cdf-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9cdf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9cdf-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9cdf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9cdf-114">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9cdf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>