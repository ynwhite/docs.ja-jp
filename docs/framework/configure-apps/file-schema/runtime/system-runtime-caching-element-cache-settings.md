---
title: "&lt;system.runtime.caching&gt;要素 (キャッシュの設定)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 83964d3a6e07267eaa946fa306301bc6d0d16e8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemruntimecachinggt-element-cache-settings"></a>&lt;system.runtime.caching&gt;要素 (キャッシュの設定)
構成ファイル内の <xref:System.Runtime.Caching.ObjectCache> エントリを使用して既定のメモリ内の `memoryCache` の実装の構成を提供します。  
  
 \<configuration>  
\<system.runtime.caching >  
  
## <a name="syntax"></a>構文  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
 `None`  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<memoryCache>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<xref:System.Runtime.Caching.MemoryCache> クラスに基づくキャッシュを構成するために使用される要素を定義します。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|共通言語ランタイムおよび [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] アプリケーションで使用されるすべての構成ファイルのルート要素です。|  
  
## <a name="remarks"></a>コメント  
 この名前空間のクラスは、ASP.NET のキャッシュ機能と同様のキャッシュ機能を使用する方法を提供しますが、 `System.Web` アセンブリに依存しません。 詳細については、「 [Caching in .NET Framework Applications](../../../../../docs/framework/performance/caching-in-net-framework-applications.md)」を参照してください。  
  
> [!NOTE]
>  <xref:System.Runtime.Caching> 名前空間の出力キャッシュ機能と型は、 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]の新機能です。  
  
## <a name="example"></a>例  
 次の例では、 <xref:System.Runtime.Caching.MemoryCache> クラスを元にしたキャッシュの構成方法を紹介します。 この例では、メモリ キャッシュ用の `namedCaches` エントリのインスタンスの構成を方法を示します。 キャッシュの名前は、 `name` 属性を "default" に設定することによって、既定のキャッシュ エントリ名に設定されます。  
  
 `cacheMemoryLimitMegabytes` 属性および `physicalMemoryPercentage` 属性はゼロに設定されます。 これらの属性をゼロに設定すると、 <xref:System.Runtime.Caching.MemoryCache> の自動サイズ調整ヒューリスティックが既定で使用されることになります。 キャッシュの実装では、現在のメモリ負荷と絶対およびパーセントのメモリ制限を 2 分ごとに比較する必要があります。  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a>参照  
 [\<memoryCache > 要素 (キャッシュの設定)](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
