---
title: "ICeeGen::GetString メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetString
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f7afe07309850a564ec75e69c07f63a3210f3810
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="b768b-102">ICeeGen::GetString メソッド</span><span class="sxs-lookup"><span data-stu-id="b768b-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="b768b-103">指定の相対仮想アドレスに格納された文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="b768b-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="b768b-104">このメソッドは、古いは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b768b-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b768b-105">構文</span><span class="sxs-lookup"><span data-stu-id="b768b-105">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in]  ULONG      RVA,   
    [out] LPWSTR     *lpString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b768b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b768b-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="b768b-107">[in]返される文字列の相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="b768b-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="b768b-108">[out]返される文字列。</span><span class="sxs-lookup"><span data-stu-id="b768b-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b768b-109">要件</span><span class="sxs-lookup"><span data-stu-id="b768b-109">Requirements</span></span>  
 <span data-ttu-id="b768b-110">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="b768b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b768b-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b768b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b768b-112">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="b768b-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b768b-113">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b768b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b768b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b768b-114">See Also</span></span>  
 [<span data-ttu-id="b768b-115">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b768b-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)