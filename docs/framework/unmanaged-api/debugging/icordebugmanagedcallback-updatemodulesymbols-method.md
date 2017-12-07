---
title: "ICorDebugManagedCallback::UpdateModuleSymbols メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.UpdateModuleSymbols
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5a1606c256bbfd3b0a7de29b84aace1b4831a016
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="0a876-102">ICorDebugManagedCallback::UpdateModuleSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="0a876-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="0a876-103">共通言語ランタイム モジュールのシンボルが変更されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="0a876-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a876-104">構文</span><span class="sxs-lookup"><span data-stu-id="0a876-104">Syntax</span></span>  
  
```  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a876-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0a876-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="0a876-106">[in]ICorDebugAppDomain を表すオブジェクトを含むモジュールのシンボルが変更されたが、アプリケーション ドメインへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0a876-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="0a876-107">[in]シンボルが変更されたが、モジュールを表す ICorDebugModule オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0a876-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="0a876-108">[in]Win32 COM へのポインター`IStream`変更済みのシンボルを格納するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0a876-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a876-109">コメント</span><span class="sxs-lookup"><span data-stu-id="0a876-109">Remarks</span></span>  
 <span data-ttu-id="0a876-110">このメソッドを呼び出すことによってモジュールのシンボルのデバッガーのビューを更新する機会を提供する[isymunmanagedreader::updatesymbolstore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)または[isymunmanagedreader::replacesymbolstore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)です。</span><span class="sxs-lookup"><span data-stu-id="0a876-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="0a876-111">このコールバックに、同じモジュールの複数回発生します。</span><span class="sxs-lookup"><span data-stu-id="0a876-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="0a876-112">デバッガーは、バインドされていないソース レベルのブレークポイントをバインドする試してください。</span><span class="sxs-lookup"><span data-stu-id="0a876-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a876-113">要件</span><span class="sxs-lookup"><span data-stu-id="0a876-113">Requirements</span></span>  
 <span data-ttu-id="0a876-114">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="0a876-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a876-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a876-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a876-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a876-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a876-117">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a876-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a876-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a876-118">See Also</span></span>  
 [<span data-ttu-id="0a876-119">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0a876-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)