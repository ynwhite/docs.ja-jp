---
title: "ISymUnmanagedReader::ReplaceSymbolStore メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1bedceac4661204bb72e59981450d7fee488857b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a>ISymUnmanagedReader::ReplaceSymbolStore メソッド
既存のシンボル ストアをデルタ シンボル ストアで置き換えます。 このメソッドがに似ていますが、 [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)メソッド、指定のデルタは、更新プログラムではなく、完全な置き換えとして機能する点が異なります。  
  
> [!NOTE]
>  1 つだけを指定する必要があります、`filename`または`pIStream`パラメーターは、両方は使用できません。 場合`filename`を指定すると、そのファイル内のシンボル、シンボル ストアが更新されます。 場合`pIStream`を指定すると、ストアからのデータで更新されます、<xref:System.Runtime.InteropServices.ComTypes.IStream>です。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `filename`  
 [in]シンボル ストアを含むファイルの名前。  
  
 `pIStream`  
 [in]代わりに使用する、ファイル ストリーム、`filename`パラメーター。  
  
## <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK、それ以外の場合、E_FAIL またはその他のエラー コード。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** CorSym.idl、CorSym.h  
  
## <a name="see-also"></a>参照  
 [ISymUnmanagedReader インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
