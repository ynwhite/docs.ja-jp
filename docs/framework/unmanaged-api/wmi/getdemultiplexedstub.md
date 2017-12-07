---
title: "GetDemultiplexedStub 関数 (アンマネージ API リファレンス)"
description: "GetDemultiplexedStub 関数では、Windows の管理から非同期呼び出しの受信をクライアントを支援するためには、オブジェクト転送シンクを作成します。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetDemultiplexedStub
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetDemultiplexedStub
helpviewer_keywords: GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a81101acbf65546ea068e6b5a0e8d9045aaadc71
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="ef115-103">GetDemultiplexedStub 関数</span><span class="sxs-lookup"><span data-stu-id="ef115-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="ef115-104">Windows の管理から非同期呼び出しの受信をクライアントを支援するためには、オブジェクト転送シンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="ef115-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ef115-105">構文</span><span class="sxs-lookup"><span data-stu-id="ef115-105">Syntax</span></span>  
  
```  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="ef115-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ef115-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="ef115-107">[in]クライアントのインプロセス実装へのポインター [IWbemObjectSink](https://msdn.microsoft.com/en-us/library/aa391787(v=vs.85).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="ef115-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](https://msdn.microsoft.com/en-us/library/aa391787(v=vs.85).aspx).</span></span>

`isLocal`  
<span data-ttu-id="ef115-108">[in]イベントがローカルかどうかを示すフラグ (`true`)、それ以外の`false`します。</span><span class="sxs-lookup"><span data-stu-id="ef115-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="ef115-109">[out]クライアントを Windows の管理から非同期呼び出しの受信を支援するためにオブジェクトの転送シンクです。</span><span class="sxs-lookup"><span data-stu-id="ef115-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="ef115-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="ef115-110">Return value</span></span>

<span data-ttu-id="ef115-111">関数が成功した場合、戻り値は`S_OK`(0) です。</span><span class="sxs-lookup"><span data-stu-id="ef115-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="ef115-112">関数が失敗した場合、戻り値がゼロ以外のエラー コードです。</span><span class="sxs-lookup"><span data-stu-id="ef115-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="ef115-113">拡張エラー情報を取得する呼び出し、 [GetErrorInfo](geterrorinfo.md)関数。</span><span class="sxs-lookup"><span data-stu-id="ef115-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="ef115-114">要件</span><span class="sxs-lookup"><span data-stu-id="ef115-114">Requirements</span></span>  
 <span data-ttu-id="ef115-115">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="ef115-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef115-116">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ef115-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ef115-117">**.NET framework のバージョン:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ef115-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef115-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef115-118">See also</span></span>  
[<span data-ttu-id="ef115-119">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="ef115-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)