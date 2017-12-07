---
title: "ISymENCUnmanagedMethod::GetDocumentsForMethod メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 951c80360153feb434d21fafe4d029a24f6cb362
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="37eee-102">ISymENCUnmanagedMethod::GetDocumentsForMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="37eee-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="37eee-103">このメソッドの行が含まれるドキュメントを取得します。</span><span class="sxs-lookup"><span data-stu-id="37eee-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37eee-104">構文</span><span class="sxs-lookup"><span data-stu-id="37eee-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,   
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37eee-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="37eee-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="37eee-106">[in]バッファーの長さを指す`pcDocs`です。</span><span class="sxs-lookup"><span data-stu-id="37eee-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="37eee-107">[out]ポインター、`ULONG32`ドキュメントの格納に必要なバッファーの文字のサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="37eee-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="37eee-108">[in]ドキュメントを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="37eee-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37eee-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="37eee-109">Return Value</span></span>  
 <span data-ttu-id="37eee-110">メソッドが成功した場合は S_OK、それ以外の場合、エラー コード。</span><span class="sxs-lookup"><span data-stu-id="37eee-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37eee-111">要件</span><span class="sxs-lookup"><span data-stu-id="37eee-111">Requirements</span></span>  
 <span data-ttu-id="37eee-112">**ヘッダー:** CorSym.idl、CorSym.h</span><span class="sxs-lookup"><span data-stu-id="37eee-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37eee-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="37eee-113">See Also</span></span>  
 [<span data-ttu-id="37eee-114">ISymENCUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="37eee-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)