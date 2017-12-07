---
title: "ICLRRuntimeHost::SetHostControl メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.SetHostControl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 932ba5577ee262b2b044fe5cd7681de1f8b459f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="941fe-102">ICLRRuntimeHost::SetHostControl メソッド</span><span class="sxs-lookup"><span data-stu-id="941fe-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="941fe-103">共通言語ランタイム (CLR) の使用時のホストの実装を取得に使用できるインターフェイス ポインターを設定[IHostControl インターフェイス](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)です。</span><span class="sxs-lookup"><span data-stu-id="941fe-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="941fe-104">構文</span><span class="sxs-lookup"><span data-stu-id="941fe-104">Syntax</span></span>  
  
```  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="941fe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="941fe-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="941fe-106">[in]ホストの実装へのインターフェイス ポインター [IHostControl インターフェイス](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)です。</span><span class="sxs-lookup"><span data-stu-id="941fe-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="941fe-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="941fe-107">Return Value</span></span>  
  
|<span data-ttu-id="941fe-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="941fe-108">HRESULT</span></span>|<span data-ttu-id="941fe-109">説明</span><span class="sxs-lookup"><span data-stu-id="941fe-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="941fe-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="941fe-110">S_OK</span></span>|<span data-ttu-id="941fe-111">`SetHostControl`正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="941fe-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="941fe-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="941fe-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="941fe-113">CLR が、プロセスに読み込まれていませんまたは CLR は、状態をマネージ コードを実行またはできないの呼び出しは正常に処理します。</span><span class="sxs-lookup"><span data-stu-id="941fe-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="941fe-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="941fe-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="941fe-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="941fe-115">The call timed out.</span></span>|  
|<span data-ttu-id="941fe-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="941fe-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="941fe-117">呼び出し元は、ロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="941fe-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="941fe-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="941fe-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="941fe-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="941fe-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="941fe-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="941fe-120">E_FAIL</span></span>|<span data-ttu-id="941fe-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="941fe-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="941fe-122">メソッドには、E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="941fe-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="941fe-123">メソッドのホストに以降の呼び出しでは、HOST_E_CLRNOTAVAILABLE を返します。</span><span class="sxs-lookup"><span data-stu-id="941fe-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="941fe-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="941fe-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="941fe-125">CLR は既に初期化されています。</span><span class="sxs-lookup"><span data-stu-id="941fe-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="941fe-126">コメント</span><span class="sxs-lookup"><span data-stu-id="941fe-126">Remarks</span></span>  
 <span data-ttu-id="941fe-127">呼び出す必要があります`SetHostControl`CLR が初期化される前に、つまり、呼び出す前に[Start メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)かのいずれかを使用して、[メタデータ インターフェイス](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)です。</span><span class="sxs-lookup"><span data-stu-id="941fe-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="941fe-128">呼び出すことをお勧め`SetHostControl`呼び出し直後後[CorBindToCurrentRuntime 関数](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)または[CorBindToRuntimeEx 関数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)です。</span><span class="sxs-lookup"><span data-stu-id="941fe-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="941fe-129">要件</span><span class="sxs-lookup"><span data-stu-id="941fe-129">Requirements</span></span>  
 <span data-ttu-id="941fe-130">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="941fe-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="941fe-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="941fe-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="941fe-132">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="941fe-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="941fe-133">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="941fe-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="941fe-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="941fe-134">See Also</span></span>  
 [<span data-ttu-id="941fe-135">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="941fe-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="941fe-136">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="941fe-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)