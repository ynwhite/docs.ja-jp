---
title: "公式の .NET Docker イメージ"
description: "コンテナーの .NET アプリケーションの .NET Microservices アーキテクチャ |公式の .NET Docker イメージ"
keywords: "Docker, マイクロサービス, ASP.NET, コンテナー"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 6f14bd0cf55a552f3881d755ebe7389f000975d8
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2017
---
# <a name="official-net-docker-images"></a><span data-ttu-id="8fa6a-104">公式の .NET Docker イメージ</span><span class="sxs-lookup"><span data-stu-id="8fa6a-104">Official .NET Docker images</span></span>

<span data-ttu-id="8fa6a-105">公式の .NET Docker イメージは、Microsoft を作成、最適化の Docker イメージです。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-105">The Official .NET Docker images are Docker images created and optimized by Microsoft.</span></span> <span data-ttu-id="8fa6a-106">上の Microsoft リポジトリに公開されている[Docker Hub](https://hub.docker.com/u/microsoft/)です。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-106">They are publicly available in the Microsoft repositories on [Docker Hub](https://hub.docker.com/u/microsoft/).</span></span> <span data-ttu-id="8fa6a-107">各リポジトリには、.NET のバージョンと、OS と (Linux Debian、Alpine Linux、Windows Nano Server、Windows Server Core など) のバージョンによって、複数のイメージを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-107">Each repository can contain multiple images, depending on .NET versions, and depending on the OS and versions (Linux Debian, Linux Alpine, Windows Nano Server, Windows Server Core, etc.).</span></span>

<span data-ttu-id="8fa6a-108">.NET リポジトリ用の Microsoft のビジョンには詳細な焦点を当てておりのリポジトリをリポジトリが特定のシナリオやワークロードを表します。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-108">Microsoft’s vision for .NET repositories is to have granular and focused repos, where a repo represents a specific scenario or workload.</span></span> <span data-ttu-id="8fa6a-109">インスタンス、 [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)開始時間を短縮それら ASP.NET Core のイメージは、さらに最適化はコンテナーを提供するため、Docker で ASP.NET Core を使用するときに、イメージを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-109">For instance, the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) images should be used when using ASP.NET Core on Docker, because those ASP.NET Core images provide additional optimizations so containers can start faster.</span></span>

<span data-ttu-id="8fa6a-110">その一方で、.NET Core イメージ (microsoft/dotnet) は、.NET Core に基づいてコンソール アプリを意図しています。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-110">On the other hand, the .NET Core images (microsoft/dotnet) are intended for console apps based on .NET Core.</span></span> <span data-ttu-id="8fa6a-111">たとえば、バッチ処理、Azure web ジョブ、およびその他のコンソール シナリオは、.NET Core を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-111">For example, batch processes, Azure WebJobs, and other console scenarios should use .NET Core.</span></span> <span data-ttu-id="8fa6a-112">それらのイメージでは、小さいコンテナーのイメージの結果として得られる、ASP.NET Core スタックは含まれません。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-112">Those images do not include the ASP.NET Core stack, resulting in a smaller container image.</span></span>

<span data-ttu-id="8fa6a-113">ほとんどのイメージ リポジトリは、だけでなく、特定のフレームワークのバージョンを選択するため、OS (Linux ディストリビューションまたは Windows のバージョン) を選択にも、広範なタグ付けを提供します。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-113">Most image repos provide extensive tagging to help you select not just a specific framework version, but also to choose an OS (Linux distro or Windows version).</span></span>

<span data-ttu-id="8fa6a-114">Microsoft が提供する公式 .NET Docker イメージの詳細については、次を参照してください。、 [.NET Docker Images 概要](https://aka.ms/dotnetdockerimages)です。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-114">For further information about the official .NET Docker images provided by Microsoft, see the [.NET Docker Images summary](https://aka.ms/dotnetdockerimages).</span></span>

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a><span data-ttu-id="8fa6a-115">.NET core と Docker のイメージの運用と開発のための最適化</span><span class="sxs-lookup"><span data-stu-id="8fa6a-115">.NET Core and Docker image optimizations for development versus production</span></span>

<span data-ttu-id="8fa6a-116">開発者向けの Docker イメージを構築するときに、Microsoft は、次の主なシナリオでフォーカスしています。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-116">When building Docker images for developers, Microsoft focused on the following main scenarios:</span></span>

-   <span data-ttu-id="8fa6a-117">使用するイメージ*開発*と .NET Core アプリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-117">Images used to *develop* and build .NET Core apps.</span></span>

-   <span data-ttu-id="8fa6a-118">使用するイメージ*実行*.NET Core アプリ。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-118">Images used to *run* .NET Core apps.</span></span>

<span data-ttu-id="8fa6a-119">なぜ複数のイメージですか?</span><span class="sxs-lookup"><span data-stu-id="8fa6a-119">Why multiple images?</span></span> <span data-ttu-id="8fa6a-120">開発、構築、およびコンテナー化アプリケーションを実行している、ときに、通常優先度が異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-120">When developing, building, and running containerized applications, you usually have different priorities.</span></span> <span data-ttu-id="8fa6a-121">これら個別のタスク、さまざまなイメージを提供することによっては、Microsoft は、開発、構築、およびアプリの展開の個別のプロセスを最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-121">By providing different images for these separate tasks, Microsoft helps optimize the separate processes of developing, building, and deploying apps.</span></span>

### <a name="during-development-and-build"></a><span data-ttu-id="8fa6a-122">開発およびビルド中には</span><span class="sxs-lookup"><span data-stu-id="8fa6a-122">During development and build</span></span>

<span data-ttu-id="8fa6a-123">開発中は、重要な点はどの程度の速度を繰り返し処理できる変更、および変更をデバッグする機能です。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-123">During development, what is important is how fast you can iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="8fa6a-124">イメージのサイズは、コードを変更して、変更をすばやく確認する機能と同じくらい重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-124">The size of the image is not as important as the ability to make changes to your code and see the changes quickly.</span></span> <span data-ttu-id="8fa6a-125">一部のツールおよび「ビルド エージェント コンテナー」開発中、の開発 ASP.NET Core のイメージ (microsoft/aspnetcore-ビルド) を使用してとプロセスをビルドします。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-125">Some tools and "build-agent containers", use the development ASP.NET Core image (microsoft/aspnetcore-build) during development and build proces.</span></span> <span data-ttu-id="8fa6a-126">Docker コンテナー内のビルド時に重要な側面は、アプリをコンパイルするために必要な要素です。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-126">When building inside a Docker container, the important aspects are the elements that are needed in order to compile your app.</span></span> <span data-ttu-id="8fa6a-127">これには、コンパイラが含まれます、その他の .NET の依存関係に加えて、npm などの web 開発の依存関係 Gulp、Bower です。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-127">This includes the compiler and any other .NET dependencies, plus web development dependencies like npm, Gulp, and Bower.</span></span>

<span data-ttu-id="8fa6a-128">この種類のビルド イメージが重要な理由</span><span class="sxs-lookup"><span data-stu-id="8fa6a-128">Why is this type of build image important?</span></span> <span data-ttu-id="8fa6a-129">実稼働環境には、このイメージは展開しません。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-129">You do not deploy this image to production.</span></span> <span data-ttu-id="8fa6a-130">代わりに、使用して実稼働のイメージに配置するコンテンツをビルドするイメージを勧めします。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-130">Instead, it is an image you use to build the content you place into a production image.</span></span> <span data-ttu-id="8fa6a-131">このイメージは、継続的インテグレーション (CI) 環境またはビルド環境で使用されます。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-131">This image would be used in your continuous integration (CI) environment or build environment.</span></span> <span data-ttu-id="8fa6a-132">たとえば、ビルド エージェントで直接、すべてのアプリケーションの依存関係を手動でインストールするのではなく VM をホスト (など)、ビルド エージェントは、アプリケーションをビルドするために必要なすべての依存関係を持つ .NET Core ビルド イメージをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-132">For instance, rather than manually installing all your application dependencies directly on a build agent host (a VM, for example), the build agent would instantiate a .NET Core build image with all the dependencies required to build the application.</span></span> <span data-ttu-id="8fa6a-133">この Docker イメージの実行方法を理解する必要があるのはビルド エージェントのみです。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-133">Your build agent only needs to know how to run this Docker image.</span></span> <span data-ttu-id="8fa6a-134">これは、CI の環境を簡略化されより予測可能になります。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-134">This simplifies your CI environment and makes it much more predictable.</span></span>

### <a name="in-production"></a><span data-ttu-id="8fa6a-135">実稼働環境で</span><span class="sxs-lookup"><span data-stu-id="8fa6a-135">In production</span></span>

<span data-ttu-id="8fa6a-136">実稼働環境で重要な点は、どの程度の速度を配置して、実稼働 .NET Core イメージに基づいて、コンテナーを開始できます。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-136">What is important in production is how fast you can deploy and start your containers based on a production .NET Core image.</span></span> <span data-ttu-id="8fa6a-137">したがって、ランタイムのみのイメージがに基づいて[microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)は上を移動できます迅速にネットワーク経由で Docker レジストリからの Docker ホストにあるために、小さいです。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-137">Therefore, the runtime-only image based on [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) is small so that it can travel quickly across the network from your Docker registry to your Docker hosts.</span></span> <span data-ttu-id="8fa6a-138">内容は、結果を処理するコンテナーの開始から時間が最速の有効化を実行する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-138">The contents are ready to run, enabling the fastest time from starting the container to processing results.</span></span> <span data-ttu-id="8fa6a-139">モデルでは、Docker、C からのコンパイルの必要はありません\#コードは、そことして、またはその dotnet 発行時に dotnet ビルドを実行するとコンテナーを使用してビルドします。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-139">In the Docker model, there is no need for compilation from C\# code, as there is when you run dotnet build or dotnet publish when using the build container.</span></span>

<span data-ttu-id="8fa6a-140">この最適化されたイメージには、バイナリのみと、アプリケーションを実行するために必要なその他のコンテンツを配置します。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-140">In this optimized image you put only the binaries and other content needed to run the application.</span></span> <span data-ttu-id="8fa6a-141">Dotnet で作成されたコンテンツの発行など、コンパイルされた .NET バイナリ、イメージ、.js、および .css ファイルのみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-141">For example, the content created by dotnet publish contains only the compiled .NET binaries, images, .js, and .css files.</span></span> <span data-ttu-id="8fa6a-142">時間の経過と共に、jit のパッケージを含むイメージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-142">Over time, you will see images that contain pre-jitted packages.</span></span>

<span data-ttu-id="8fa6a-143">.NET Core および ASP.NET Core のイメージの複数のバージョンがありますが、これらはすべて基本レイヤーを含む 1 つまたは複数のレイヤーを共有します。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-143">Although there are multiple versions of the .NET Core and ASP.NET Core images, they all share one or more layers, including the base layer.</span></span> <span data-ttu-id="8fa6a-144">そのため、イメージの格納に必要なディスク領域量が少ないです。カスタム イメージとその基本画像間のデルタののみで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-144">Therefore, the amount of disk space needed to store an image is small; it consists only of the delta between your custom image and its base image.</span></span> <span data-ttu-id="8fa6a-145">レジストリからイメージをプルする簡単であることになります。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-145">The result is that it is quick to pull the image from your registry.</span></span>

<span data-ttu-id="8fa6a-146">Docker Hub に .NET イメージ リポジトリを探索するときに、分類またはタグでマークされた複数のイメージのバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-146">When you explore the .NET image repositories at Docker Hub, you will find multiple image versions classified or marked with tags.</span></span> <span data-ttu-id="8fa6a-147">これらのタグは、使用するにはバージョンによっては、次の表に示すように、必要な決定に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8fa6a-147">These tags help to decide which one to use, depending on the version you need, like those in the following table:</span></span>

-   <span data-ttu-id="8fa6a-148">microsoft/**aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="8fa6a-148">microsoft/**aspnetcore:2.0**</span></span>

        ASP.NET Core, with runtime only and ASP.NET Core optimizations, on Linux and Windows (multi-arch)

-   <span data-ttu-id="8fa6a-149">microsoft/**aspnetcore-ビルド: 2.0**</span><span class="sxs-lookup"><span data-stu-id="8fa6a-149">microsoft/**aspnetcore-build:2.0**</span></span>

        ASP.NET Core, with SDKs included, on Linux and Windows (multi-arch)


>[!div class="step-by-step"]
<span data-ttu-id="8fa6a-150">[前](net-コンテナーの os-targets.md) [次へ] (../architect-microservice-container-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="8fa6a-150">[Previous] (net-container-os-targets.md) [Next] (../architect-microservice-container-applications/index.md)</span></span>