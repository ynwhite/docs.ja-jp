---
title: "ICorPublishProcessEnum インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcessEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcessEnum
helpviewer_keywords: ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 66e31911289d1ef8b590a0b7e7896adfa4998adc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="e5753-102">ICorPublishProcessEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5753-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="e5753-103">サブクラス、 [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)のコレクションを走査するメソッドを提供するインターフェイス[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e5753-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5753-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e5753-104">Methods</span></span>  
  
|<span data-ttu-id="e5753-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e5753-105">Method</span></span>|<span data-ttu-id="e5753-106">説明</span><span class="sxs-lookup"><span data-stu-id="e5753-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5753-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="e5753-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="e5753-108">指定した数を取得`ICorPublishProcess`コレクションの現在位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="e5753-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5753-109">コメント</span><span class="sxs-lookup"><span data-stu-id="e5753-109">Remarks</span></span>  
 <span data-ttu-id="e5753-110">`ICorPublishProcessEnum`インターフェイス抽象、インターフェイスのメソッドを実装[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)です。</span><span class="sxs-lookup"><span data-stu-id="e5753-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="e5753-111">`ICorPublishProcessEnum`インスタンスを作成した、 [icorpublish::enumprocesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)メソッドです。</span><span class="sxs-lookup"><span data-stu-id="e5753-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="e5753-112">コレクションのトラバース`ICorPublishProcess`オブジェクトは、時に指定されたフィルター条件に基づいて、`ICorPublishProcessEnum`インスタンスが作成されました。</span><span class="sxs-lookup"><span data-stu-id="e5753-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5753-113">要件</span><span class="sxs-lookup"><span data-stu-id="e5753-113">Requirements</span></span>  
 <span data-ttu-id="e5753-114">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="e5753-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5753-115">**ヘッダー:** CorPub.idl、CorPub.h</span><span class="sxs-lookup"><span data-stu-id="e5753-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e5753-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5753-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5753-117">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5753-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5753-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5753-118">See Also</span></span>  
 [<span data-ttu-id="e5753-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5753-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="e5753-120">CorpubPublish コクラス</span><span class="sxs-lookup"><span data-stu-id="e5753-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)