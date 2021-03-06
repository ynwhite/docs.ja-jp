---
title: "ICorDebugStepper::StepOut メソッド"
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
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d6462f166e9c734dacc7ebee13cb82e3b12158b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperstepout-method"></a>ICorDebugStepper::StepOut メソッド
Icordebugstepper シングル ステップ実行に現在のフレームが呼び出し元のフレームに制御を返すときに完了してその格納スレッドを表示します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>コメント  
 A`StepOut`呼び出し元のフレームを現在のフレームから正常に返る後に操作を完了します。  
  
 場合`StepOut`時に呼び出される、現在のフレームが呼び出し元のマネージ コードに戻るときに、アンマネージ コードでステップを行います。  
  
 .NET Framework version 2.0 では使用しないで`StepOut`STOP_UNMANAGED フラグをセットが失敗するためです。 (使用[icordebugstepper::setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)ステッピングのフラグを設定します)。相互運用機能デバッガー必要があります [ステップ アウト] ネイティブ コードに自体です。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
