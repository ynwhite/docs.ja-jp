---
title: "F# の型"
description: "F# および f# の型をという名前し、説明されている方法で使用される型について説明します。"
keywords: "visual f#, f#, 関数型プログラミング"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c7272a0d-5ab6-4eae-bceb-e49af498b917
ms.openlocfilehash: 9b7235637f301f91ae2cc8fbc59adc27cdfd5bd0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="f-types"></a><span data-ttu-id="e3d37-104">F# の型</span><span class="sxs-lookup"><span data-stu-id="e3d37-104">F# Types</span></span>

<span data-ttu-id="e3d37-105">このトピックでは、f# および f# の型をという名前し、説明されている方法で使用される型について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-105">This topic describes the types that are used in F# and how F# types are named and described.</span></span>


## <a name="summary-of-f-types"></a><span data-ttu-id="e3d37-106">F# の型の概要</span><span class="sxs-lookup"><span data-stu-id="e3d37-106">Summary of F# Types</span></span>
<span data-ttu-id="e3d37-107">いくつかの型と見なされます*プリミティブ型*、ブール型など`bool`とバイト数と文字の型を含む、さまざまなサイズの整数と浮動小数点型です。</span><span class="sxs-lookup"><span data-stu-id="e3d37-107">Some types are considered *primitive types*, such as the Boolean type `bool` and integral and floating point types of various sizes, which include types for bytes and characters.</span></span> <span data-ttu-id="e3d37-108">これらの型は「[プリミティブ型](primitive-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="e3d37-108">These types are described in [Primitive Types](primitive-types.md).</span></span>

<span data-ttu-id="e3d37-109">言語に組み込まれている他の種類は、組、リスト、配列、シーケンス、レコードが含まれてし、判別共用体です。</span><span class="sxs-lookup"><span data-stu-id="e3d37-109">Other types that are built into the language include tuples, lists, arrays, sequences, records, and discriminated unions.</span></span> <span data-ttu-id="e3d37-110">他の .NET 言語の使用経験があり学習の F# では場合、は、これらの型の各トピックを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3d37-110">If you have experience with other .NET languages and are learning F#, you should read the topics for each of these types.</span></span> <span data-ttu-id="e3d37-111">これらの型に関する詳細情報へのリンクが記載されて、[関連トピック](https://msdn.microsoft.com/library/#rel)このトピックの「します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-111">Links to more information about these types are included in the [Related Topics](https://msdn.microsoft.com/library/#rel) section of this topic.</span></span> <span data-ttu-id="e3d37-112">F# でこれらの特定の種類が関数型プログラミング言語に共通するスタイルのプログラミングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e3d37-112">These F#-specific types support styles of programming that are common to functional programming languages.</span></span> <span data-ttu-id="e3d37-113">これらの型の多くは、これらの型での一般的な操作をサポートしている f# ライブラリ内のモジュールを関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="e3d37-113">Many of these types have associated modules in the F# library that support common operations on these types.</span></span>

<span data-ttu-id="e3d37-114">関数の型は、パラメーターの型に関する情報が含まれていて、型を返します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-114">The type of a function includes information about the parameter types and return type.</span></span>

<span data-ttu-id="e3d37-115">.NET Framework は、オブジェクト型、インターフェイス型、デリゲート型、および他のユーザーのソースです。</span><span class="sxs-lookup"><span data-stu-id="e3d37-115">The .NET Framework is the source of object types, interface types, delegate types, and others.</span></span> <span data-ttu-id="e3d37-116">他の .NET 言語と同様、独自のオブジェクトの種類を定義できます。</span><span class="sxs-lookup"><span data-stu-id="e3d37-116">You can define your own object types just as you can in any other .NET language.</span></span>

<span data-ttu-id="e3d37-117">また、f# コードでは名前付きのエイリアスを定義できます*省略名を入力*型の代替名であります。</span><span class="sxs-lookup"><span data-stu-id="e3d37-117">Also, F# code can define aliases, which are named *type abbreviations*, that are alternative names for types.</span></span> <span data-ttu-id="e3d37-118">型が、今後変更可能性があり、型に依存するコードを変更しないようにする型の省略形を使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3d37-118">You might use type abbreviations when the type might change in the future and you want to avoid changing the code that depends on the type.</span></span> <span data-ttu-id="e3d37-119">または、コードを読み、理解を容易にすることができます、型のフレンドリ名として型の省略形を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3d37-119">Or, you might use a type abbreviation as a friendly name for a type that can make code easier to read and understand.</span></span>

<span data-ttu-id="e3d37-120">F# 関数型プログラミングの注意のように設計された便利コレクション型を提供します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-120">F# provides useful collection types that are designed with functional programming in mind.</span></span> <span data-ttu-id="e3d37-121">これらのコレクション型を使用すると、スタイルのより高機能なコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="e3d37-121">Using these collection types helps you write code that is more functional in style.</span></span> <span data-ttu-id="e3d37-122">詳細については、次を参照してください。 [f# コレクション型](fsharp-collection-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="e3d37-122">For more information, see [F# Collection Types](fsharp-collection-types.md).</span></span>


## <a name="syntax-for-types"></a><span data-ttu-id="e3d37-123">型の構文</span><span class="sxs-lookup"><span data-stu-id="e3d37-123">Syntax for Types</span></span>
<span data-ttu-id="e3d37-124">F# コードで多くの場合、型の名前を記述する必要です。</span><span class="sxs-lookup"><span data-stu-id="e3d37-124">In F# code, you often have to write out the names of types.</span></span> <span data-ttu-id="e3d37-125">すべての型は構文の形式を持ち、型の注釈は、抽象メソッドの宣言、デリゲートの宣言、署名、およびその他の構文でこれらの構文形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-125">Every type has a syntactic form, and you use these syntactic forms in type annotations, abstract method declarations, delegate declarations, signatures, and other constructs.</span></span> <span data-ttu-id="e3d37-126">インタープリターで新しいプログラム コンス トラクターを宣言するたびにその型の構造と構文の名前が出力されます。</span><span class="sxs-lookup"><span data-stu-id="e3d37-126">Whenever you declare a new program construct in the interpreter, the interpreter prints the name of the construct and the syntax for its type.</span></span> <span data-ttu-id="e3d37-127">この構文は、ユーザー定義型の単なる識別子または組み込み識別子としてのような可能性があります`int`または`string`がより複雑な型の場合は、構文は複雑です。</span><span class="sxs-lookup"><span data-stu-id="e3d37-127">This syntax might be just an identifier for a user-defined type or a built-in identifier such as for `int` or `string`, but for more complex types, the syntax is more complex.</span></span>

<span data-ttu-id="e3d37-128">次の表は、f# の型の型の構文の側面を示します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-128">The following table shows aspects of the type syntax for F# types.</span></span>



|<span data-ttu-id="e3d37-129">型</span><span class="sxs-lookup"><span data-stu-id="e3d37-129">Type</span></span>|<span data-ttu-id="e3d37-130">型の構文</span><span class="sxs-lookup"><span data-stu-id="e3d37-130">Type syntax</span></span>|<span data-ttu-id="e3d37-131">例</span><span class="sxs-lookup"><span data-stu-id="e3d37-131">Examples</span></span>|
|----|-----------|--------|
|<span data-ttu-id="e3d37-132">プリミティブ型</span><span class="sxs-lookup"><span data-stu-id="e3d37-132">primitive type</span></span>|<span data-ttu-id="e3d37-133">*型名*</span><span class="sxs-lookup"><span data-stu-id="e3d37-133">*type-name*</span></span>|`int`<br /><br />`float`<br /><br />`string`|
|<span data-ttu-id="e3d37-134">集計の種類 (クラス、構造体、共用体、レコード、列挙型、およびなど)</span><span class="sxs-lookup"><span data-stu-id="e3d37-134">aggregate type (class, structure, union, record, enum, and so on)</span></span>|<span data-ttu-id="e3d37-135">*型名*</span><span class="sxs-lookup"><span data-stu-id="e3d37-135">*type-name*</span></span>|`System.DateTime`<br /><br />`Color`|
|<span data-ttu-id="e3d37-136">型略称</span><span class="sxs-lookup"><span data-stu-id="e3d37-136">type abbreviation</span></span>|<span data-ttu-id="e3d37-137">*型略称名*</span><span class="sxs-lookup"><span data-stu-id="e3d37-137">*type-abbreviation-name*</span></span>|`bigint`|
|<span data-ttu-id="e3d37-138">完全修飾型</span><span class="sxs-lookup"><span data-stu-id="e3d37-138">fully qualified type</span></span>|<span data-ttu-id="e3d37-139">*namespaces.type 名*</span><span class="sxs-lookup"><span data-stu-id="e3d37-139">*namespaces.type-name*</span></span><br /><br /><span data-ttu-id="e3d37-140">または</span><span class="sxs-lookup"><span data-stu-id="e3d37-140">or</span></span><br /><br /><span data-ttu-id="e3d37-141">*modules.type 名*</span><span class="sxs-lookup"><span data-stu-id="e3d37-141">*modules.type-name*</span></span><br /><br /><span data-ttu-id="e3d37-142">または</span><span class="sxs-lookup"><span data-stu-id="e3d37-142">or</span></span><br /><br /><span data-ttu-id="e3d37-143">*namespaces.modules.type 名*</span><span class="sxs-lookup"><span data-stu-id="e3d37-143">*namespaces.modules.type-name*</span></span>|`System.IO.StreamWriter`|
|<span data-ttu-id="e3d37-144">array</span><span class="sxs-lookup"><span data-stu-id="e3d37-144">array</span></span>|<span data-ttu-id="e3d37-145">*型名*、または</span><span class="sxs-lookup"><span data-stu-id="e3d37-145">*type-name*[] or</span></span><br /><br /><span data-ttu-id="e3d37-146">*型名*配列</span><span class="sxs-lookup"><span data-stu-id="e3d37-146">*type-name* array</span></span>|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|<span data-ttu-id="e3d37-147">2 次元配列</span><span class="sxs-lookup"><span data-stu-id="e3d37-147">two-dimensional array</span></span>|<span data-ttu-id="e3d37-148">*型名*[、]</span><span class="sxs-lookup"><span data-stu-id="e3d37-148">*type-name*[,]</span></span>|`int[,]`<br /><br />`float[,]`|
|<span data-ttu-id="e3d37-149">3 次元配列</span><span class="sxs-lookup"><span data-stu-id="e3d37-149">three-dimensional array</span></span>|<span data-ttu-id="e3d37-150">*型名*[、]</span><span class="sxs-lookup"><span data-stu-id="e3d37-150">*type-name*[,,]</span></span>|`float[,,]`|
|<span data-ttu-id="e3d37-151">tuple</span><span class="sxs-lookup"><span data-stu-id="e3d37-151">tuple</span></span>|<span data-ttu-id="e3d37-152">*型 name1* &#42;です。*型 name2*しています.</span><span class="sxs-lookup"><span data-stu-id="e3d37-152">*type-name1* &#42; *type-name2* ...</span></span>|<span data-ttu-id="e3d37-153">たとえば、`(1,'b',3)`型を持つ`int * char * int`</span><span class="sxs-lookup"><span data-stu-id="e3d37-153">For example, `(1,'b',3)` has type `int * char * int`</span></span>|
|<span data-ttu-id="e3d37-154">ジェネリック型</span><span class="sxs-lookup"><span data-stu-id="e3d37-154">generic type</span></span>|<span data-ttu-id="e3d37-155">*型パラメーター* *ジェネリック型名*</span><span class="sxs-lookup"><span data-stu-id="e3d37-155">*type-parameter* *generic-type-name*</span></span><br /><br /><span data-ttu-id="e3d37-156">または</span><span class="sxs-lookup"><span data-stu-id="e3d37-156">or</span></span><br /><br /><span data-ttu-id="e3d37-157">*ジェネリック型名*&lt;*型のパラメーター リスト*&gt;</span><span class="sxs-lookup"><span data-stu-id="e3d37-157">*generic-type-name*&lt;*type-parameter-list*&gt;</span></span>|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|<span data-ttu-id="e3d37-158">構築された型 (を指定する特定の型引数を持つジェネリック型)</span><span class="sxs-lookup"><span data-stu-id="e3d37-158">constructed type (a generic type that has a specific type argument supplied)</span></span>|<span data-ttu-id="e3d37-159">*型引数**ジェネリック型名*</span><span class="sxs-lookup"><span data-stu-id="e3d37-159">*type-argument* *generic-type-name*</span></span><br /><br /><span data-ttu-id="e3d37-160">または</span><span class="sxs-lookup"><span data-stu-id="e3d37-160">or</span></span><br /><br /><span data-ttu-id="e3d37-161">*ジェネリック型名*&lt;*型引数リスト*&gt;</span><span class="sxs-lookup"><span data-stu-id="e3d37-161">*generic-type-name*&lt;*type-argument-list*&gt;</span></span>|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|<span data-ttu-id="e3d37-162">1 つのパラメーターを持つ関数の型</span><span class="sxs-lookup"><span data-stu-id="e3d37-162">function type that has a single parameter</span></span>|<span data-ttu-id="e3d37-163">*パラメーター-type1*  - &gt; *戻り値の型*</span><span class="sxs-lookup"><span data-stu-id="e3d37-163">*parameter-type1* -&gt; *return-type*</span></span>|<span data-ttu-id="e3d37-164">受け取る関数、`int`を返します、`string`型を持つ`int -> string`</span><span class="sxs-lookup"><span data-stu-id="e3d37-164">A function that takes an `int` and returns a `string` has type `int -> string`</span></span>|
|<span data-ttu-id="e3d37-165">複数のパラメーターを持つ関数の型</span><span class="sxs-lookup"><span data-stu-id="e3d37-165">function type that has multiple parameters</span></span>|<span data-ttu-id="e3d37-166">*パラメーター-type1*  - &gt; *パラメーター type2*  - &gt; ... -&gt; *戻り値の型*</span><span class="sxs-lookup"><span data-stu-id="e3d37-166">*parameter-type1* -&gt; *parameter-type2* -&gt; ... -&gt; *return-type*</span></span>|<span data-ttu-id="e3d37-167">受け取る関数、`int`と`float`を返します、`string`型を持つ`int -> float -> string`</span><span class="sxs-lookup"><span data-stu-id="e3d37-167">A function that takes an `int` and a `float` and returns a `string` has type `int -> float -> string`</span></span>|
|<span data-ttu-id="e3d37-168">高階関数をパラメーターとして</span><span class="sxs-lookup"><span data-stu-id="e3d37-168">higher order function as a parameter</span></span>|<span data-ttu-id="e3d37-169">(*関数型*)</span><span class="sxs-lookup"><span data-stu-id="e3d37-169">(*function-type*)</span></span>|<span data-ttu-id="e3d37-170">`List.map`型があります。`('a -> 'b) -> 'a list -> 'b list`</span><span class="sxs-lookup"><span data-stu-id="e3d37-170">`List.map` has type `('a -> 'b) -> 'a list -> 'b list`</span></span>|
|<span data-ttu-id="e3d37-171">delegate</span><span class="sxs-lookup"><span data-stu-id="e3d37-171">delegate</span></span>|<span data-ttu-id="e3d37-172">委任*関数型*</span><span class="sxs-lookup"><span data-stu-id="e3d37-172">delegate of *function-type*</span></span>|`delegate of unit -> int`|
|<span data-ttu-id="e3d37-173">フレキシブル型</span><span class="sxs-lookup"><span data-stu-id="e3d37-173">flexible type</span></span>|<span data-ttu-id="e3d37-174">#*型名*</span><span class="sxs-lookup"><span data-stu-id="e3d37-174">#*type-name*</span></span>|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a><span data-ttu-id="e3d37-175">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e3d37-175">Related Topics</span></span>


|<span data-ttu-id="e3d37-176">トピック</span><span class="sxs-lookup"><span data-stu-id="e3d37-176">Topic</span></span>|<span data-ttu-id="e3d37-177">説明</span><span class="sxs-lookup"><span data-stu-id="e3d37-177">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="e3d37-178">プリミティブ型</span><span class="sxs-lookup"><span data-stu-id="e3d37-178">Primitive Types</span></span>](primitive-types.md)|<span data-ttu-id="e3d37-179">整数型、ブール型、および文字型などの組み込みの単純型について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-179">Describes built-in simple types such as integral types, the Boolean type, and character types.</span></span>|
|[<span data-ttu-id="e3d37-180">Unit 型</span><span class="sxs-lookup"><span data-stu-id="e3d37-180">Unit Type</span></span>](unit-type.md)|<span data-ttu-id="e3d37-181">について説明します、`unit`型、1 つの値を持つし、() で示されている型と等価です`void`C# の場合と`Nothing`Visual Basic でします。</span><span class="sxs-lookup"><span data-stu-id="e3d37-181">Describes the `unit` type, a type that has one value and that is indicated by (); equivalent to `void` in C# and `Nothing` in Visual Basic.</span></span>|
|[<span data-ttu-id="e3d37-182">タプル</span><span class="sxs-lookup"><span data-stu-id="e3d37-182">Tuples</span></span>](tuples.md)|<span data-ttu-id="e3d37-183">任意の型のペア、組、4 倍、およびようにグループ化に関連する値で構成される型は、タプル型について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-183">Describes the tuple type, a type that consists of associated values of any type grouped in pairs, triples, quadruples, and so on.</span></span>|
|[<span data-ttu-id="e3d37-184">オプション</span><span class="sxs-lookup"><span data-stu-id="e3d37-184">Options</span></span>](options.md)|<span data-ttu-id="e3d37-185">オプションの種類、する可能性がありますが、値か、空にする型について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-185">Describes the option type, a type that may either have a value or be empty.</span></span>|
|[<span data-ttu-id="e3d37-186">リスト</span><span class="sxs-lookup"><span data-stu-id="e3d37-186">Lists</span></span>](lists.md)|<span data-ttu-id="e3d37-187">説明リストで、順序付けられ、変更できない一連の要素は、すべて同じ型のです。</span><span class="sxs-lookup"><span data-stu-id="e3d37-187">Describes lists, which are ordered, immutable series of elements all of the same type.</span></span>|
|[<span data-ttu-id="e3d37-188">配列</span><span class="sxs-lookup"><span data-stu-id="e3d37-188">Arrays</span></span>](arrays.md)|<span data-ttu-id="e3d37-189">配列で、連続するメモリ ブロックを占有し、固定サイズは、同じ種類の変更可能な要素のセットは順序付けについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-189">Describes arrays, which are ordered sets of mutable elements of the same type that occupy a contiguous block of memory and are of fixed size.</span></span>|
|[<span data-ttu-id="e3d37-190">シーケンス</span><span class="sxs-lookup"><span data-stu-id="e3d37-190">Sequences</span></span>](sequences.md)|<span data-ttu-id="e3d37-191">論理の一連の値を表すシーケンスの種類について説明します個々 の値は、必要な場合だけが計算されます。</span><span class="sxs-lookup"><span data-stu-id="e3d37-191">Describes the sequence type, which represents a logical series of values; individual values are computed only as necessary.</span></span>|
|[<span data-ttu-id="e3d37-192">レコード</span><span class="sxs-lookup"><span data-stu-id="e3d37-192">Records</span></span>](records.md)|<span data-ttu-id="e3d37-193">レコードの種類、名前付きの値の小さい集計について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-193">Describes the record type, a small aggregate of named values.</span></span>|
|[<span data-ttu-id="e3d37-194">判別共用体</span><span class="sxs-lookup"><span data-stu-id="e3d37-194">Discriminated Unions</span></span>](discriminated-unions.md)|<span data-ttu-id="e3d37-195">判別共用体型の値を持つ一連の可能な型のいずれかを指定できます型について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-195">Describes the discriminated union type, a type whose values can be any one of a set of possible types.</span></span>|
|[<span data-ttu-id="e3d37-196">関数</span><span class="sxs-lookup"><span data-stu-id="e3d37-196">Functions</span></span>](functions/index.md)|<span data-ttu-id="e3d37-197">関数の値について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-197">Describes function values.</span></span>|
|[<span data-ttu-id="e3d37-198">クラス</span><span class="sxs-lookup"><span data-stu-id="e3d37-198">Classes</span></span>](classes.md)|<span data-ttu-id="e3d37-199">クラス型を .NET 参照型に対応するオブジェクトの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-199">Describes the class type, an object type that corresponds to a .NET reference type.</span></span> <span data-ttu-id="e3d37-200">クラスの型には、メンバー、プロパティ、実装されるインターフェイスおよび基本型を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e3d37-200">Class types can contain members, properties, implemented interfaces, and a base type.</span></span>|
|[<span data-ttu-id="e3d37-201">構造体</span><span class="sxs-lookup"><span data-stu-id="e3d37-201">Structures</span></span>](structures.md)|<span data-ttu-id="e3d37-202">について説明します、 `struct` .NET 値型に対応するオブジェクト型の型。</span><span class="sxs-lookup"><span data-stu-id="e3d37-202">Describes the `struct` type, an object type that corresponds to a .NET value type.</span></span> <span data-ttu-id="e3d37-203">`struct`型は、通常、データの小さな集計を表します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-203">The `struct` type usually represents a small aggregate of data.</span></span>|
|[<span data-ttu-id="e3d37-204">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e3d37-204">Interfaces</span></span>](interfaces.md)|<span data-ttu-id="e3d37-205">特定の機能を提供するが、データを含まないメンバーのセットを表す型がインターフェイスの型について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-205">Describes interface types, which are types that represent a set of members that provide certain functionality but that contain no data.</span></span> <span data-ttu-id="e3d37-206">有用であるオブジェクトの種類によってインターフェイス型を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3d37-206">An interface type must be implemented by an object type to be useful.</span></span>|
|[<span data-ttu-id="e3d37-207">デリゲート</span><span class="sxs-lookup"><span data-stu-id="e3d37-207">Delegates</span></span>](delegates.md)|<span data-ttu-id="e3d37-208">オブジェクトとして関数を表すデリゲートの型について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-208">Describes the delegate type, which represents a function as an object.</span></span>|
|[<span data-ttu-id="e3d37-209">列挙型</span><span class="sxs-lookup"><span data-stu-id="e3d37-209">Enumerations</span></span>](enumerations.md)|<span data-ttu-id="e3d37-210">名前付きの値のセットに属している値を持つ列挙型について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-210">Describes enumeration types, whose values belong to a set of named values.</span></span>|
|[<span data-ttu-id="e3d37-211">属性</span><span class="sxs-lookup"><span data-stu-id="e3d37-211">Attributes</span></span>](attributes.md)|<span data-ttu-id="e3d37-212">別の型のメタデータを指定するための属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-212">Describes attributes, which are used to specify metadata for another type.</span></span>|
|[<span data-ttu-id="e3d37-213">例外の種類</span><span class="sxs-lookup"><span data-stu-id="e3d37-213">Exception Types</span></span>](exception-handling/exception-types.md)|<span data-ttu-id="e3d37-214">エラー情報を指定の例外について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3d37-214">Describes exceptions, which specify error information.</span></span>|