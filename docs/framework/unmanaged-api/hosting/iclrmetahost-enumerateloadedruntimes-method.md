---
title: "ICLRMetaHost::EnumerateLoadedRuntimes メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.EnumerateLoadedRuntimes
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e0724bf44eaf82b39262876ea4a44509b6c7d576
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="b2539-102">ICLRMetaHost::EnumerateLoadedRuntimes メソッド</span><span class="sxs-lookup"><span data-stu-id="b2539-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="b2539-103">含む有効な列挙体を返します[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)特定のプロセスに読み込まれている共通言語ランタイム (CLR) の各バージョン用のインターフェイス ポインター。</span><span class="sxs-lookup"><span data-stu-id="b2539-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="b2539-104">このメソッドは、 [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="b2539-104">This method supersedes the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2539-105">構文</span><span class="sxs-lookup"><span data-stu-id="b2539-105">Syntax</span></span>  
  
```  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2539-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b2539-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="b2539-107">[in]検査するプロセスのハンドルには、ランタイムが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="b2539-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="b2539-108">[out]<!--zz <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown>--> `Microsoft.VisualStudio.OLE.Interop.IEnumUnknown`の列挙体[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)プロセスによって読み込まれる各 CLR に対応するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="b2539-108">[out] An <!--zz <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown>--> `Microsoft.VisualStudio.OLE.Interop.IEnumUnknown` enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2539-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="b2539-109">Return Value</span></span>  
 <span data-ttu-id="b2539-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="b2539-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b2539-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2539-111">HRESULT</span></span>|<span data-ttu-id="b2539-112">説明</span><span class="sxs-lookup"><span data-stu-id="b2539-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2539-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2539-113">S_OK</span></span>|<span data-ttu-id="b2539-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="b2539-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="b2539-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b2539-115">E_POINTER</span></span>|<span data-ttu-id="b2539-116">`ppEnumerator` が null です。</span><span class="sxs-lookup"><span data-stu-id="b2539-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2539-117">コメント</span><span class="sxs-lookup"><span data-stu-id="b2539-117">Remarks</span></span>  
 <span data-ttu-id="b2539-118">非推奨の関数となど、読み込まれていた場合でも、このメソッドはすべて一覧表示します読み込まれたランタイム[CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2539-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2539-119">要件</span><span class="sxs-lookup"><span data-stu-id="b2539-119">Requirements</span></span>  
 <span data-ttu-id="b2539-120">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2539-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2539-121">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="b2539-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b2539-122">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="b2539-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2539-123">**.NET framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2539-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2539-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2539-124">See Also</span></span>  
 [<span data-ttu-id="b2539-125">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2539-125">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="b2539-126">ホスティング</span><span class="sxs-lookup"><span data-stu-id="b2539-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)