---
title: "&lt;supportedRuntime&gt;要素"
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 4b0967790f2bbf8fa9a889c56fa9c5168f7523bd
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2018
---
# <a name="ltsupportedruntimegt-element"></a>&lt;supportedRuntime&gt;要素

アプリケーションでサポートされる共通言語ランタイムのバージョンを指定します。 バージョン 1.1 以降の .NET Framework で構築されたすべてのアプリケーションでは、この要素を使用する必要があります。  
  
[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
&nbsp;&nbsp;[\<startup>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**  
  
## <a name="syntax"></a>構文
  
```xml  
<supportedRuntime version="runtime version" sku="sku id"/>  
```  
  
## <a name="attributes"></a>属性
  
|属性|説明|  
|---------------|-----------------|  
|**version**|省略可能な属性です。<br /><br /> このアプリケーションがサポートする共通言語ランタイム (CLR: Common Language Runtime) のバージョンを指定する文字列値。 有効な値について、`version`属性を参照してください、 [「ランタイム バージョン」値](#version)セクションです。 **注:** 、.NET Framework 3.5 を"*ランタイム バージョン*"形式の値は*メジャー*.*マイナー*.*ビルド*です。 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 以降では、必要となるのはメジャー バージョン番号とマイナー バージョン番号のみです (つまり、"v4.0.30319" ではなく "v4.0")。 短い文字列を使用することをお勧めします。|  
|**sku**|省略可能な属性です。<br /><br /> 在庫管理単位 (SKU) を指定する文字列の値。SKU はこのアプリケーションがサポートする .NET Framework リリースを指定します。<br /><br /> 使用、.NET Framework 4.0 以降、`sku`属性をお勧めします。  この属性が指定される場合は、アプリケーションが対象とする .NET Framework のバージョンを示します。<br /><br /> Sku 属性の有効な値は、次を参照してください。、 ["sku id"値](#sku)セクションです。|  
  
## <a name="remarks"></a>コメント

場合、  **\<supportedRuntime >**要素が、アプリケーション構成ファイルに存在しない、アプリケーションをビルドするために使用するランタイムのバージョンを使用します。  

**\<SupportedRuntime >** 1.1 以降、ランタイムのバージョンを使用して構築されたすべてのアプリケーションで要素を使用する必要があります。 ランタイムのバージョン 1.0 をサポートするために構築されたアプリケーションを使用する必要があります、 [ \<requiredRuntime >](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)要素。  
  
> [!NOTE]
>  使用する場合、 [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)構成ファイルを指定する関数を使用する必要があります、`<requiredRuntime>`ランタイムのすべてのバージョンの要素。 `<supportedRuntime>`を使用するときに、要素は無視されます[CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)です。  
  
NET Framework 1.1 から 3.5 までのランタイムの複数のバージョンをサポートするアプリケーションでは、ランタイムの複数のバージョンをサポートする場合は、最初の要素で最も優先度の高いバージョンを指定し、最後の要素で最も優先度の低いバージョンを指定する必要があります。 .NET Framework 4.0 またはそれ以降のバージョンをサポートするアプリ、`version`属性は、.NET Framework 4 およびそれ以降のバージョンに共通するが、CLR のバージョンを示します、`sku`属性が 1 つの .NET Framework のバージョンを示すをアプリターゲット。  
  
> [!NOTE]
>  アプリケーションがなど、レガシ アクティブ化のパスを使用するかどうか、 [CorBindToRuntimeEx 関数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)、それらのパスを以前のバージョンではなく CLR の version 4 をアクティブ化して、アプリケーションが、でビルドされた場合または[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]依存関係を持ちますに、.NET Framework の以前のバージョンでビルドされた混合モード アセンブリには不十分を指定する、[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]サポートされているランタイムの一覧にします。 さらに、 [\<スタートアップ > 要素](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)、構成ファイルに設定する必要があります、`useLegacyV2RuntimeActivationPolicy`属性を`true`です。 ただし、この属性を `true` に設定することは、以前のバージョンの .NET Framework でビルドされたすべてのコンポーネントが、それらのビルドに使用されたランタイムではなく、[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] を使用して実行されることを意味します。  
  
アプリケーションは、そのアプリケーションを実行できる .NET Framework のすべてのバージョンでテストすることをお勧めします。  
  
<a name="version"></a>   
## <a name="runtime-version-values"></a>"ランタイム バージョン" の値  
`runtime`属性が特定のアプリケーションに必要な共通言語ランタイム (CLR) バージョンを指定します。 すべてのバージョンの .NET Framework v4.x 指定、 `v4.0` CLR です。 次の表に、有効な値を*ランタイム バージョン*の値、`version`属性。  

|.NET Framework のバージョン|`version` 属性|  
|----------------------------|-------------------------|  
|1|"v1.0.3705"|  
|1.1|"v1.1.4322"|  
|2.0|"v2.0.50727"|  
|3.0|"v2.0.50727"|  
|3.5|"v2.0.50727"|  
|4.0-4.7.1|"v4.0"|  

<a name="sku"></a>   
## <a name="sku-id-values"></a>"sku id" の値

`sku`属性では、ターゲット フレームワーク モニカー (TFM) を使用して、アプリをターゲットし、実行に必要とする .NET Framework のバージョンを示します。 次の表に、有効な値でサポートされている、`sku`属性に、.NET Framework 4 以降でします。
  
|.NET Framework のバージョン|`sku` 属性|  
|----------------------------|---------------------|  
|4.0|".NETFramework,Version=v4.0"|  
|4.0、Client Profile|".NETFramework,Version=v4.0,Profile=Client"|  
|4.0、プラットフォームの更新プログラム 1|.NETFramework,Version=v4.0.1|  
|4.0、Client Profile、更新プログラム 1|.NETFramework,Version=v4.0.1,Profile=Client|  
|4.0、プラットフォームの更新プログラム 2|.NETFramework,Version=v4.0.2|  
|4.0、Client Profile、更新プログラム 2|.NETFramework,Version=v4.0.2,Profile=Client|  
|4.0、プラットフォームの更新プログラム 3|.NETFramework,Version=v4.0.3|  
|4.0、Client Profile、更新プログラム 3|.NETFramework,Version=v4.0.3,Profile=Client|  
|4.5|".NETFramework,Version=v4.5"|  
|4.5.1|".NETFramework,Version=v4.5.1"|  
|4.5.2|".NETFramework,Version=v4.5.2"|  
|4.6|".NETFramework,Version=v4.6"|  
|4.6.1|".NETFramework,Version=v4.6.1"|  
|4.6.2|".NETFramework,Version=v4.6.2"|  
|4.7|".NETFramework,Version=v4.7"|
|4.7.1|".NETFramework,Version=v4.7.1"|

## <a name="example"></a>例  
 サポートされているランタイムのバージョンを構成ファイルで指定する例を次に示します。 構成ファイルでは、アプリの対象 .NET Framework 4.7 であることを示します。  
  
```xml  
<configuration>  
   <startup>  
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />  
   </startup>  
</configuration>  
```  
  
## <a name="configuration-file"></a>構成ファイル

この要素は、アプリケーション構成ファイルで使用できます。

## <a name="see-also"></a>関連項目

 [スタートアップ設定スキーマ](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [構成ファイル スキーマ](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [インプロセスの side-by-side 実行](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)  
