---
title: Segurança
description: Arquitetando aplicativos .NET nativos da nuvem para o Azure | Segurança
ms.date: 06/30/2019
ms.openlocfilehash: 848255de70038798417a558543d0b1ea8cff1e37
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184767"
---
# <a name="security"></a><span data-ttu-id="75040-103">Segurança</span><span class="sxs-lookup"><span data-stu-id="75040-103">Security</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="75040-104">Não é um dia em que a notícia não contém alguma história sobre uma empresa que está sendo invadida ou, de alguma forma, está perdendo os dados dos clientes.</span><span class="sxs-lookup"><span data-stu-id="75040-104">Not a day goes by where the news doesn't contain some story about a company being hacked or somehow losing their customers' data.</span></span> <span data-ttu-id="75040-105">Até mesmo os países não estão imunes aos problemas criados por tratar a segurança como uma prioridade.</span><span class="sxs-lookup"><span data-stu-id="75040-105">Even countries aren't immune to the problems created by treating security as an afterthought.</span></span> <span data-ttu-id="75040-106">Durante anos, as empresas trataram da segurança dos dados do cliente e, de fato, de suas redes inteiras como algo de "bom para ter".</span><span class="sxs-lookup"><span data-stu-id="75040-106">For years, companies have treated the security of customer data and, in fact, their entire networks as something of a "nice to have".</span></span> <span data-ttu-id="75040-107">Os servidores Windows foram deixados sem patches, as versões anteriores do PHP eram mantidas em execução e os bancos de dados MongoDB deixaram de ser abertos para o mundo.</span><span class="sxs-lookup"><span data-stu-id="75040-107">Windows servers were left unpatched, ancient versions of PHP kept running and MongoDB databases left wide open to the world.</span></span>

<span data-ttu-id="75040-108">No entanto, está começando a ser consequências do mundo real para não manter uma mentalidade de segurança ao criar e implantar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="75040-108">However, there are starting to be real-world consequences for not maintaining a security mindset when building and deploying applications.</span></span> <span data-ttu-id="75040-109">Muitas empresas aprenderam a maneira difícil o que pode acontecer quando servidores e desktops não são corrigidos durante o surto de 2017 de [NotPetya](https://www.wired.com/story/notpetya-cyberattack-ukraine-russia-code-crashed-the-world/).</span><span class="sxs-lookup"><span data-stu-id="75040-109">Many companies learned the hard way what can happen when servers and desktops aren't patched during the 2017 outbreak of [NotPetya](https://www.wired.com/story/notpetya-cyberattack-ukraine-russia-code-crashed-the-world/).</span></span> <span data-ttu-id="75040-110">O custo desses ataques foi facilmente acessado em bilhões, com algumas estimativas que colocam as perdas desse único ataque a US $10.000.000.000 dólares.</span><span class="sxs-lookup"><span data-stu-id="75040-110">The cost of these attacks has easily reached into the billions, with some estimates putting the losses from this single attack at 10 billion US dollars.</span></span>

<span data-ttu-id="75040-111">Mesmo os governos não estão imunes a incidentes de hackers.</span><span class="sxs-lookup"><span data-stu-id="75040-111">Even governments aren't immune to hacking incidents.</span></span> <span data-ttu-id="75040-112">A cidade do Baltimore foi mantida por [criminosos](https://www.vox.com/recode/2019/5/21/18634505/baltimore-ransom-robbinhood-mayor-jack-young-hackers) , tornando impossível para os cidadãos pagar suas contas ou usar os serviços de cidade.</span><span class="sxs-lookup"><span data-stu-id="75040-112">The city of Baltimore was held ransom by [criminals](https://www.vox.com/recode/2019/5/21/18634505/baltimore-ransom-robbinhood-mayor-jack-young-hackers) making it impossible for citizens to pay their bills or use city services.</span></span>

<span data-ttu-id="75040-113">Também houve um aumento na legislação que exige determinadas proteções de dados para dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="75040-113">There has also been an increase in legislation that mandates certain data protections for personal data.</span></span> <span data-ttu-id="75040-114">Na Europa, a GDPR esteve em vigor por mais de um ano e, mais recentemente, a Califórnia passou sua própria versão chamada CCDA, que entra em vigor em 1º de janeiro de 2020.</span><span class="sxs-lookup"><span data-stu-id="75040-114">In Europe, GDPR has been in effect for more than a year and, more recently, California passed their own version called CCDA, which comes into effect January 1, 2020.</span></span> <span data-ttu-id="75040-115">As multas em GDPR podem ser punishing para colocar as empresas fora de negócios.</span><span class="sxs-lookup"><span data-stu-id="75040-115">The fines under GDPR can be so punishing as to put companies out of business.</span></span> <span data-ttu-id="75040-116">O Google já foi multas 50 milhões euros para violações, mas isso é apenas uma queda no Bucket em comparação com as possíveis multas.</span><span class="sxs-lookup"><span data-stu-id="75040-116">Google has already been fined 50 million Euros for violations, but that's just a drop in the bucket compared with the potential fines.</span></span>

<span data-ttu-id="75040-117">Em suma, a segurança é um negócio sério.</span><span class="sxs-lookup"><span data-stu-id="75040-117">In short, security is serious business.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="75040-118">[Anterior](identity-server.md)
>[Próximo](azure-security.md)</span><span class="sxs-lookup"><span data-stu-id="75040-118">[Previous](identity-server.md)
[Next](azure-security.md)</span></span>