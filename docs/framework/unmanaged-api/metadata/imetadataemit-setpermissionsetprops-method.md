---
title: "IMetaDataEmit::SetPermissionSetProps メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetPermissionSetProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5666daff143d261160bb90bf31c98d1e1b7ce270
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="9d2cd-102">IMetaDataEmit::SetPermissionSetProps メソッド</span><span class="sxs-lookup"><span data-stu-id="9d2cd-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="9d2cd-103">設定または前回の呼び出しによって定義されたアクセス許可セットのメタデータ署名の機能を更新[imetadataemit::definepermissionset](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)です。</span><span class="sxs-lookup"><span data-stu-id="9d2cd-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d2cd-104">構文</span><span class="sxs-lookup"><span data-stu-id="9d2cd-104">Syntax</span></span>  
  
```  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d2cd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9d2cd-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="9d2cd-106">[in]装飾するオブジェクトを表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="9d2cd-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="9d2cd-107">[in]A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md)を使用する宣言型セキュリティの種類を示す値。</span><span class="sxs-lookup"><span data-stu-id="9d2cd-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="9d2cd-108">[in]アクセス許可 BLOB。</span><span class="sxs-lookup"><span data-stu-id="9d2cd-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="9d2cd-109">[in]サイズをバイト単位での`pvPermission`します。</span><span class="sxs-lookup"><span data-stu-id="9d2cd-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="9d2cd-110">[out]`mdPermission`更新されたアクセス許可を表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="9d2cd-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d2cd-111">要件</span><span class="sxs-lookup"><span data-stu-id="9d2cd-111">Requirements</span></span>  
 <span data-ttu-id="9d2cd-112">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="9d2cd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d2cd-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9d2cd-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d2cd-114">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="9d2cd-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d2cd-115">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d2cd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d2cd-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d2cd-116">See Also</span></span>  
 [<span data-ttu-id="9d2cd-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9d2cd-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="9d2cd-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9d2cd-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)