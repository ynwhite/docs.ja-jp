---
title: "クイック スタート - クラスの概要 - C# ガイド"
description: "初めての C# プログラムを作成し、オブジェクト指向の概念を確認します"
author: billwagner
ms.author: wiwagn
ms.date: 10/11/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: ad6e83d427b55482f9615e0083682bdca6c56704
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="introduction-to-classes"></a><span data-ttu-id="5e14a-103">クラスの概要</span><span class="sxs-lookup"><span data-stu-id="5e14a-103">Introduction to classes</span></span>

<span data-ttu-id="5e14a-104">このレッスンでは、ご利用の環境に [.NET Core SDK](http://dot.net/core) と任意のエディターがインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="5e14a-104">This lesson assumes that you've installed [.NET Core SDK](http://dot.net/core), and an editor of your choice.</span></span> <span data-ttu-id="5e14a-105">インストールされていない場合は、Mac または Windows の [Visual Studio Code](https://code.visualstudio.com/) または [Visual Studio](https://www.visualstudio.com/) をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="5e14a-105">If you don't have one, try [Visual Studio Code](https://code.visualstudio.com/), or [Visual Studio](https://www.visualstudio.com/) on Mac or Windows.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="5e14a-106">アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="5e14a-106">Create your application</span></span>

<span data-ttu-id="5e14a-107">ターミナル ウィンドウで、「**classes**」という名前のディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-107">Using a terminal window, create a directory named **classes**.</span></span> <span data-ttu-id="5e14a-108">ここにアプリケーションを構築します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-108">You'll build your application there.</span></span> <span data-ttu-id="5e14a-109">このディレクトリに移動し、コンソール ウィンドウで「`dotnet new console`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-109">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="5e14a-110">このコマンドにより、アプリケーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-110">This command creates your application.</span></span> <span data-ttu-id="5e14a-111">**Program.cs** を開きます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-111">Open **Program.cs**.</span></span> <span data-ttu-id="5e14a-112">内容は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5e14a-112">It should look like this:</span></span>

```csharp
using System;

namespace classes
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="5e14a-113">このクイック スタートでは、銀行口座を表す新しい型を作成します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-113">In this quick start, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="5e14a-114">通常、開発者は各クラスを別々のテキスト ファイルで定義します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-114">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="5e14a-115">この方法なら、プログラムのサイズが大きくなっても管理が容易です。</span><span class="sxs-lookup"><span data-stu-id="5e14a-115">That makes it easier to manage as a program grows in size.</span></span>  <span data-ttu-id="5e14a-116">**classes** ディレクトリに「**BankAccount.cs**」という名前の新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-116">Create a new file named **BankAccount.cs** in the **classes** directory.</span></span> 

<span data-ttu-id="5e14a-117">このファイルには、***銀行口座***の定義が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-117">This file will contain the deefinition of a ***bank account***.</span></span> <span data-ttu-id="5e14a-118">オブジェクト指向プログラミングでは、***クラス***の形式で型を作成することによりコードを整理します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-118">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="5e14a-119">これらのクラスには、特定のエンティティを表すコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e14a-119">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="5e14a-120">`BankAccount` クラスは銀行口座を表します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-120">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="5e14a-121">コードでは、メソッドとプロパティを使用した特定の操作を実装します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-121">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="5e14a-122">このクイック スタートでは、銀行口座は次の内容をサポートします。</span><span class="sxs-lookup"><span data-stu-id="5e14a-122">In this quick start, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="5e14a-123">銀行口座を一意に特定する 10 桁の数字をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5e14a-123">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="5e14a-124">口座の名前、または所有者の名前を格納する文字列をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5e14a-124">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="5e14a-125">残高を取得できます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-125">The balance can be retrieved.</span></span>
1. <span data-ttu-id="5e14a-126">預金を許可します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-126">It accepts deposits.</span></span>
1. <span data-ttu-id="5e14a-127">引き出しを許可します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-127">It accepts withdrawals.</span></span>
1. <span data-ttu-id="5e14a-128">初期残高は正の値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e14a-128">The initial balance must be positive.</span></span>
1. <span data-ttu-id="5e14a-129">引き出しによって残高が負の値になることはありません。</span><span class="sxs-lookup"><span data-stu-id="5e14a-129">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="5e14a-130">銀行口座の型を定義する</span><span class="sxs-lookup"><span data-stu-id="5e14a-130">Define the bank account type</span></span>

<span data-ttu-id="5e14a-131">動作を定義するクラスの基本を作成することから開始できます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-131">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="5e14a-132">内容は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5e14a-132">It would look like this:</span></span>

```csharp
using System;

namespace classes
{
    public class BankAccount
    {
        public string Number { get; }
        public string Owner { get; set; }
        public decimal Balance { get; }

        public void MakeDeposit(decimal amount, DateTime date, string note)
        {
        }

        public void MakeWithdrawal(decimal amount, DateTime date, string payee, string note)
        {
        }
    }
}
```

<span data-ttu-id="5e14a-133">先に進む前に、構築したものを確認してみましょう。</span><span class="sxs-lookup"><span data-stu-id="5e14a-133">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="5e14a-134">`namespace` 宣言は、コードを論理的に整理する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-134">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="5e14a-135">このクイック スタートで取り扱うコードは比較的小さいため、1 つの名前空間にすべてのコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-135">This quick start is relatively small, so you'll put all the code in one namespace.</span></span> 

<span data-ttu-id="5e14a-136">`public class BankAccount` は、これから作成するクラスまたは型を定義します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-136">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="5e14a-137">クラス宣言のあとにある `{` と `}` の内側はすべて、クラスの動作を定義しています。</span><span class="sxs-lookup"><span data-stu-id="5e14a-137">Everything inside the `{` and `}` that follows the class declaration defines the behavior of the class.</span></span> <span data-ttu-id="5e14a-138">`BankAccount` クラスには、5 つの***メンバー***があります。</span><span class="sxs-lookup"><span data-stu-id="5e14a-138">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="5e14a-139">最初の 3 つは***プロパティ***です。</span><span class="sxs-lookup"><span data-stu-id="5e14a-139">The first three are ***properties***.</span></span> <span data-ttu-id="5e14a-140">プロパティはデータ要素であり、検証やその他の規則を適用するコードを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-140">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="5e14a-141">最後の 2 つは***メソッド***です。</span><span class="sxs-lookup"><span data-stu-id="5e14a-141">The last two are ***methods***.</span></span> <span data-ttu-id="5e14a-142">メソッドは 1 つの関数を実行するコード ブロックです。</span><span class="sxs-lookup"><span data-stu-id="5e14a-142">Methods are blocks of code that peform a single function.</span></span> <span data-ttu-id="5e14a-143">各メンバーの名前を確認すると、開発者がそのクラスの作用を把握するための十分な情報が得られます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-143">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="5e14a-144">新しいアカウントを開く</span><span class="sxs-lookup"><span data-stu-id="5e14a-144">Open a new account</span></span>

<span data-ttu-id="5e14a-145">実装する最初の機能は、銀行口座を開く機能です。</span><span class="sxs-lookup"><span data-stu-id="5e14a-145">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="5e14a-146">顧客が口座を開く場合、初期残高や口座の (1 名または複数名の) 所有者の情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e14a-146">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span> 

<span data-ttu-id="5e14a-147">`BankAccount` 型の新しいオブジェクトを作成すると、これらの値を割り当てる***コンストラクター***が定義されます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-147">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="5e14a-148">***コンストラクター***はクラスと同じ名前のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="5e14a-148">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="5e14a-149">これは、そのクラス型のオブジェクトを初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-149">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="5e14a-150">`BankAccount` 型に次のコンストラクターを追加します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-150">Add the following constructor to the `BankAccount` type:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="5e14a-151">[`new`](../language-reference/keywords/new.md) を使用してオブジェクトを作成すると、コンストラクターが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-151">Constructors are called when you create an object using [`new`](../language-reference/keywords/new.md).</span></span> <span data-ttu-id="5e14a-152">***program.cs*** の `Console.WriteLine("Hello World!");` の行を次の行で置き換えます (`<name>` を自分の名前に置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="5e14a-152">Replace the line `Console.WriteLine("Hello World!");` in ***program.cs*** with the following line (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="5e14a-153">「`dotnet run`」と入力すると何が起こるか見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="5e14a-153">Type `dotnet run` to see what happens.</span></span>  

<span data-ttu-id="5e14a-154">口座番号が空であることに気付かれましたか? </span><span class="sxs-lookup"><span data-stu-id="5e14a-154">Did you notice that the account number is blank?</span></span> <span data-ttu-id="5e14a-155">次にこの問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-155">It's time to fix that.</span></span> <span data-ttu-id="5e14a-156">口座番号はオブジェクトが作成されるときに割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e14a-156">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="5e14a-157">しかし、それを作成する責任を呼び出し元に負わせるべきではありません。</span><span class="sxs-lookup"><span data-stu-id="5e14a-157">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="5e14a-158">`BankAccount` クラスのコードは、新しい口座番号の割り当て方を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e14a-158">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="5e14a-159">そのための簡単な方法は、10 桁の数字で始めることです。</span><span class="sxs-lookup"><span data-stu-id="5e14a-159">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="5e14a-160">そして、新しい口座番号が作成されるごとに値を 1 増加します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-160">Increment it when each new account is created.</span></span> <span data-ttu-id="5e14a-161">最後に、オブジェクトが作成されるときに現在の口座番号を格納します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-161">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="5e14a-162">`BankAccount` クラスに次のメンバー宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-162">Add the following member declaration to the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="5e14a-163">これがデータ メンバーです。</span><span class="sxs-lookup"><span data-stu-id="5e14a-163">This is a data member.</span></span> <span data-ttu-id="5e14a-164">これは `private` であり、`BankAccount` クラス内のコードのみがこれにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-164">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="5e14a-165">この方法により、プライベートな実装 (口座番号の生成方法) から (口座番号を持つなどの) パブリックな責任を分離できます。次の 2 行をコンストラクターに追加して、口座番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-165">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated.) Add the following two lines to the constructor to assign the account number:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="5e14a-166">「`dotnet run`」と入力して結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-166">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="5e14a-167">預金と引き出しを作成する</span><span class="sxs-lookup"><span data-stu-id="5e14a-167">Create deposits and withdrawals</span></span>

<span data-ttu-id="5e14a-168">銀行口座クラスは、預金と引き出しを許可して正しく動作するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e14a-168">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="5e14a-169">口座のすべてのトランザクションを記録する履歴を作成して、預金と引き出しを実装しましょう。</span><span class="sxs-lookup"><span data-stu-id="5e14a-169">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="5e14a-170">これには、単純にトランザクションごとに残高を更新する方法に比べていくつかのメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="5e14a-170">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="5e14a-171">履歴は、すべてのトランザクションを監査して毎日の残高を管理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-171">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="5e14a-172">必要に応じてすべてのトランザクションの履歴から残高を計算することにより、1 つのトランザクションの中で修正されたすべてのエラーが正しく残高に反映されて次の計算に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-172">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="5e14a-173">トランザクションを表す新しい型を作成するところから始めましょう。</span><span class="sxs-lookup"><span data-stu-id="5e14a-173">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="5e14a-174">これは一切の責任を持たない単純型です。</span><span class="sxs-lookup"><span data-stu-id="5e14a-174">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="5e14a-175">いくつかのプロパティが必要になります。</span><span class="sxs-lookup"><span data-stu-id="5e14a-175">It needs a few properties.</span></span> <span data-ttu-id="5e14a-176">「***Transaction.cs***」という名前の新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-176">Create a new file named ***Transaction.cs***.</span></span> <span data-ttu-id="5e14a-177">これに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-177">Add the following code to it:</span></span>

[!code-csharp[Transaction](../../../samples/csharp/classes-quickstart/Transaction.cs "Transaction declaration")]

<span data-ttu-id="5e14a-178">`BankAccount` クラスに `Transaction` オブジェクトの <xref:System.Collections.Generic.List%601> を追加しましょう。</span><span class="sxs-lookup"><span data-stu-id="5e14a-178">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="5e14a-179">次の宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-179">Add the following declaration:</span></span>

[!code-csharp[TransactionDecl](../../../samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration "Transaction declaration")]

<span data-ttu-id="5e14a-180"><xref:System.Collections.Generic.List%601> クラスでは、別の名前空間をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e14a-180">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="5e14a-181">**BankAccount.cs** の最初に次を追加します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-181">Add the following at the beginning of **BankAccount.cs**:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="5e14a-182">`Balance` の報告方法を変更しましょう。</span><span class="sxs-lookup"><span data-stu-id="5e14a-182">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="5e14a-183">これは、すべてのトランザクションの値を合計することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-183">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="5e14a-184">`BankAccount` クラスの `Balance` の宣言を次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-184">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](../../../samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation "Computing the balance")]

<span data-ttu-id="5e14a-185">この例は、***プロパティ***の重要な一面を示しています。</span><span class="sxs-lookup"><span data-stu-id="5e14a-185">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="5e14a-186">これで、別のプログラマーが値を要求したときに残高が計算されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5e14a-186">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="5e14a-187">この計算処理は、すべてのトランザクションを列挙して、その合計値を現在の残高として提供します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-187">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="5e14a-188">次に `MakeDeposit` メソッドと `MakeWithdrawal` メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-188">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="5e14a-189">これらのメソッドは、初期残高が正の値でなければならず、引き出し後の残高が負の値になってはいけない、という最後の 2 つの規則を適用します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-189">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span> 

<span data-ttu-id="5e14a-190">これにより、***例外***の概念が導入されます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-190">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="5e14a-191">メソッドが作業を正常に完了できないことを示す標準的な方法は、例外をスローすることです。</span><span class="sxs-lookup"><span data-stu-id="5e14a-191">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="5e14a-192">例外の型とそれに関連付けられたメッセージがエラーを説明します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-192">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="5e14a-193">`MakeDeposit` メソッドは、預金額が負の値になる場合に例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="5e14a-193">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="5e14a-194">`MakeWithdrawal` メソッドは、引き出し額が負の値になる場合、または引き出しを適用した結果、残高が負の値になる場合に例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="5e14a-194">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance:</span></span>

[!code-csharp[DepositAndWithdrawal](../../../samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal "Make deposits and withdrawals")]

<span data-ttu-id="5e14a-195">[`throw`](../language-reference/keywords/throw.md) ステートメントが例外を**スロー**します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-195">The [`throw`](../language-reference/keywords/throw.md) statement **throws** an exception.</span></span> <span data-ttu-id="5e14a-196">現在のメソッドの実行が終了し、一致する `catch` ブロックが見つかったときに再開します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-196">Execution of the current method ends, and will resume when a matching `catch` block is found.</span></span> <span data-ttu-id="5e14a-197">あとで `catch` ブロックを追加してこのコードをテストします。</span><span class="sxs-lookup"><span data-stu-id="5e14a-197">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="5e14a-198">残高を直接更新するのではなく、最初のトランザクションを追加するようにするため、コンストラクターを 1 か所変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e14a-198">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="5e14a-199">既に `MakeDeposit` メソッドは記述したので、このメソッドをコンストラクターから呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-199">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="5e14a-200">完成したコンストラクターは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5e14a-200">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](../../../samples/csharp/classes-quickstart/BankAccount.cs#Constructor "The final version of the constructor")]

<span data-ttu-id="5e14a-201"><xref:System.DateTime.Now?displayProperty=nameWithType> は、現在の日付と時刻を返すプロパティです。</span><span class="sxs-lookup"><span data-stu-id="5e14a-201"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="5e14a-202">`Main` メソッドにいくつかの預金と引き出しを追加することで、これをテストします。</span><span class="sxs-lookup"><span data-stu-id="5e14a-202">Test this by adding a few deposits and withdrawals in your `Main` method:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="5e14a-203">次に、残高が負の値になっているアカウントを作成してみることで、エラー条件のキャッチをテストします。</span><span class="sxs-lookup"><span data-stu-id="5e14a-203">Next, test that you are catching error conditions by trying to create an account with a negative balance:</span></span>

```csharp
// Test that the initial balances must be positive:
try {
    var invalidAccount = new BankAccount("invalid", -55);
} catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="5e14a-204">[`try` と `catch` のステートメント](../language-reference/keywords/try-catch.md)を使用して、例外をスローする可能性のあるコード ブロックをマークし、想定したエラーをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="5e14a-204">You use the [`try` and `catch` statements](../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions, and to catch those errors that you expect.</span></span> <span data-ttu-id="5e14a-205">同じ方法で、残高が負の値になっている場合にスローを行うコードをテストします。</span><span class="sxs-lookup"><span data-stu-id="5e14a-205">You can use the same technique to test the code that throws for a negative balance:</span></span>

```csharp
// Test for a negative balance
try {
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
} catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="5e14a-206">ファイルを保存し、「`dotnet run`」と入力して試します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-206">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="5e14a-207">課題 - すべてのトランザクションをログに記録する</span><span class="sxs-lookup"><span data-stu-id="5e14a-207">Challenge - log all transactions</span></span>

<span data-ttu-id="5e14a-208">このクイック スタートを完了すると、トランザクション履歴の `string` を作成する `GetAccountHistory` メソッドを記述できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5e14a-208">To finish this quick start, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="5e14a-209">このメソッドを `BankAccount` 型に追加します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-209">add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](../../../samples/csharp/classes-quickstart/BankAccount.cs#History "Display transaction history")]

<span data-ttu-id="5e14a-210">これは、<xref:System.Text.StringBuilder> クラスを使用して、各トランザクションを 1 行で表す文を含んだ文字列をフォーマットします。</span><span class="sxs-lookup"><span data-stu-id="5e14a-210">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="5e14a-211">文字列をフォーマットするコードについては、このクイック スタートで先述しました。</span><span class="sxs-lookup"><span data-stu-id="5e14a-211">You've seen the string formatting code earlier in these quick starts.</span></span> <span data-ttu-id="5e14a-212">新しい文字の 1 つは `\t` です。</span><span class="sxs-lookup"><span data-stu-id="5e14a-212">One new character is `\t`.</span></span> <span data-ttu-id="5e14a-213">これはタブを挿入して出力をフォーマットします。</span><span class="sxs-lookup"><span data-stu-id="5e14a-213">That inserts a tab to format the output.</span></span>

<span data-ttu-id="5e14a-214">次の行を追加して、**Program.cs** でテストします。</span><span class="sxs-lookup"><span data-stu-id="5e14a-214">Add this line to test it in **Program.cs**:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="5e14a-215">「`dotnet run`」と入力して結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="5e14a-215">Type `dotnet run` to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5e14a-216">次の手順</span><span class="sxs-lookup"><span data-stu-id="5e14a-216">Next Steps</span></span>

<span data-ttu-id="5e14a-217">うまくいかない場合は、このクイック スタートのソースを [GitHub リポジトリ](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="5e14a-217">If you got stuck, you can see the source for this quick start [in our GitHub repo](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/)</span></span>

<span data-ttu-id="5e14a-218">おつかれさまでした。クイック スタートはこれで終了です。</span><span class="sxs-lookup"><span data-stu-id="5e14a-218">Congratulations, you've finished all our Quick Starts.</span></span> <span data-ttu-id="5e14a-219">さらに詳しい情報については、[チュートリアル](../tutorials/index.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5e14a-219">If you're eager to learn more, try our [tutorials](../tutorials/index.md)</span></span>