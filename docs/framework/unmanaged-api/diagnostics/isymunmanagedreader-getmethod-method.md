---
title: "ISymUnmanagedReader::GetMethod メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 94c40555ee62bac99cf7cb34378c5b0fcca5104f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="d59ff-102">ISymUnmanagedReader::GetMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="d59ff-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="d59ff-103">メソッドのトークンを指定、シンボル リーダー メソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="d59ff-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d59ff-104">構文</span><span class="sxs-lookup"><span data-stu-id="d59ff-104">Syntax</span></span>  
  
```  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d59ff-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d59ff-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="d59ff-106">[in]メソッド トークンです。</span><span class="sxs-lookup"><span data-stu-id="d59ff-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d59ff-107">[out]返されたインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d59ff-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d59ff-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="d59ff-108">Return Value</span></span>  
 <span data-ttu-id="d59ff-109">メソッドが成功した場合は S_OK、それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="d59ff-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d59ff-110">要件</span><span class="sxs-lookup"><span data-stu-id="d59ff-110">Requirements</span></span>  
 <span data-ttu-id="d59ff-111">**ヘッダー:** CorSym.idl、CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d59ff-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d59ff-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d59ff-112">See Also</span></span>  
 [<span data-ttu-id="d59ff-113">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d59ff-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)