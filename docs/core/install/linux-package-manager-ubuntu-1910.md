---
title: Instalar o .NET Core no Ubuntu 19,10 Package Manager-.NET Core
description: Use um Gerenciador de pacotes para instalar SDK do .NET Core e tempo de execução no Ubuntu 19,10.
author: thraka
ms.author: adegeo
ms.date: 01/16/2020
ms.openlocfilehash: b8fec2afa6f03e3dabbf1ff449431759087163ba
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920635"
---
# <a name="ubuntu-1910-package-manager---install-net-core"></a><span data-ttu-id="b8529-103">Gerenciador de pacotes do Ubuntu 19,10 – instalar o .NET Core</span><span class="sxs-lookup"><span data-stu-id="b8529-103">Ubuntu 19.10 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="b8529-104">Este artigo descreve como usar um Gerenciador de pacotes para instalar o .NET Core no Ubuntu 19,10.</span><span class="sxs-lookup"><span data-stu-id="b8529-104">This article describes how to use a package manager to install .NET Core on Ubuntu 19.10.</span></span> <span data-ttu-id="b8529-105">Se você estiver instalando o tempo de execução, sugerimos que instale o [ASP.NET Core Runtime](#install-the-aspnet-core-runtime), pois ele inclui o .NET Core e ASP.NET Core Runtimes.</span><span class="sxs-lookup"><span data-stu-id="b8529-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="b8529-106">Registrar chave e feed da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b8529-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="b8529-107">Antes de instalar o .NET, você precisará:</span><span class="sxs-lookup"><span data-stu-id="b8529-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="b8529-108">Registre a chave da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b8529-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="b8529-109">Registre o repositório do produto.</span><span class="sxs-lookup"><span data-stu-id="b8529-109">Register the product repository.</span></span>
- <span data-ttu-id="b8529-110">Instale as dependências necessárias.</span><span class="sxs-lookup"><span data-stu-id="b8529-110">Install required dependencies.</span></span>

<span data-ttu-id="b8529-111">Isso só precisa ser feito uma vez por computador.</span><span class="sxs-lookup"><span data-stu-id="b8529-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="b8529-112">Abra um terminal e execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="b8529-112">Open a terminal and run the following commands.</span></span>

```bash
wget -q https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="b8529-113">Instalar o SDK do .NET Core</span><span class="sxs-lookup"><span data-stu-id="b8529-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="b8529-114">Atualize os produtos disponíveis para instalação e, em seguida, instale o SDK do .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b8529-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="b8529-115">Em seu terminal, execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="b8529-115">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="b8529-116">Se você receber uma mensagem de erro semelhante a **não é possível localizar o pacote dotnet-SDK-3,1**, consulte a seção [solucionar problemas do Gerenciador de pacotes](#troubleshoot-the-package-manager) .</span><span class="sxs-lookup"><span data-stu-id="b8529-116">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="b8529-117">Instalar o ASP.NET Core Runtime</span><span class="sxs-lookup"><span data-stu-id="b8529-117">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="b8529-118">Atualize os produtos disponíveis para instalação e instale o ASP.NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="b8529-118">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="b8529-119">Em seu terminal, execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="b8529-119">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="b8529-120">Se você receber uma mensagem de erro semelhante a **não é possível localizar o pacote aspnetcore-Runtime-3,1**, consulte a seção [solucionar problemas do Gerenciador de pacotes](#troubleshoot-the-package-manager) .</span><span class="sxs-lookup"><span data-stu-id="b8529-120">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="b8529-121">Instalar o tempo de execução do .NET Core</span><span class="sxs-lookup"><span data-stu-id="b8529-121">Install the .NET Core runtime</span></span>

<span data-ttu-id="b8529-122">Atualize os produtos disponíveis para instalação e, em seguida, instale o tempo de execução do .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b8529-122">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="b8529-123">Em seu terminal, execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="b8529-123">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="b8529-124">Se você receber uma mensagem de erro semelhante a **não é possível localizar o pacote dotnet-Runtime-3,1**, consulte a seção [solucionar problemas do Gerenciador de pacotes](#troubleshoot-the-package-manager) .</span><span class="sxs-lookup"><span data-stu-id="b8529-124">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="b8529-125">Como instalar outras versões</span><span class="sxs-lookup"><span data-stu-id="b8529-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="b8529-126">Solucionar problemas do Gerenciador de pacotes</span><span class="sxs-lookup"><span data-stu-id="b8529-126">Troubleshoot the package manager</span></span>

<span data-ttu-id="b8529-127">Esta seção fornece informações sobre erros comuns que você pode obter ao usar o Gerenciador de pacotes para instalar o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b8529-127">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="b8529-128">Não é possível localizar</span><span class="sxs-lookup"><span data-stu-id="b8529-128">Unable to locate</span></span>

<span data-ttu-id="b8529-129">Se você receber uma mensagem de erro semelhante a **não é possível localizar o pacote {The .NET Core Package}** , execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="b8529-129">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="b8529-130">Se isso não funcionar, você poderá executar uma instalação manual com os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="b8529-130">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget -q https://packages.microsoft.com/config/ubuntu/19.10/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="b8529-131">Falha ao buscar</span><span class="sxs-lookup"><span data-stu-id="b8529-131">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]