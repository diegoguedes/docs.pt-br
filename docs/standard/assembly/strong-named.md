---
title: Assemblies de nome forte
description: Saiba mais sobre nomes fortes para assemblies do .NET, que cria uma identidade exclusiva para um assembly e pode evitar conflitos de assembly.
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, about strong-named assemblies
- assemblies [.NET Framework], strong-named
ms.assetid: d4a80263-f3e0-4d81-9b61-f0cbeae3797b
ms.openlocfilehash: a2db0efcb57226a757796c311309ce8f749a398b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378606"
---
# <a name="strong-named-assemblies"></a>Assemblies de nome forte

Uma nomeação forte na assembly cria uma única identidade para assembly e pode evitar conflitos de assembly.

## <a name="what-makes-a-strong-named-assembly"></a>Como é criado um assembly de nomeação forte?

Um assembly de nome forte é gerado por meio da utilização de uma chave privada que corresponde a uma chave pública distribuída com o assembly e por ele mesmo. O assembly inclui o manifesto assembly que contém os nomes e os hashes de todos os arquivos que compõem o assembly. Assemblies que têm o mesmo nome forte devem ser idênticos.

Você pode usar nomes fortes nos assemblies usando o Visual Studio ou uma ferramenta de linha de comando. Para obter mais informações, consulte [como assinar um assembly com um nome forte](sign-strong-name.md) ou [sn. exe (ferramenta Strong Name)](../../framework/tools/sn-exe-strong-name-tool.md).

Quando um assembly de nome forte é criado, ele contém o nome de texto simples do assembly, o número de versão, informação cultural opcional, uma assinatura digital e uma chave pública que corresponde a uma chave privada utilizada para assinar.

> [!WARNING]
> Por segurança, não confie em nomes fortes. Eles apenas fornecem uma identidade exclusiva.

## <a name="why-strong-name-your-assemblies"></a>Por que usar um nome forte em seus assemblies?

Quando você usa um assembly de nome forte como referência, espera obter determinados benefícios, como controle de versão e proteção de nomenclatura. No .NET Framework, os assemblies de nome forte podem ser instalados no cache de assembly global, que é necessário para habilitar alguns cenários.

Assemblies de nome forte são úteis nos seguintes cenários:

- Você deseja habilitar seus assemblies a serem referenciados por assemblies de nome forte ou para dar acesso `friend` aos seus assemblies de outros assemblies de nome forte.

- Um aplicativo precisa acessar versões diferentes do mesmo assembly. Isso significa que você precisa de versões diferentes de um assembly para carregar lado a lado no mesmo domínio de aplicativo sem conflitos. Por exemplo, se extensões diferentes de uma API existirem em assemblies que tenham o mesmo nome simples, nomeações fortes fornecem uma identidade única para cada versão de assembly.

- Você não deseja afetar negativamente o desempenho de aplicativos usando o assembly, por isso assembly deve ser neutros quanto ao domínio. Isso exige uma nomeação forte porque um assembly com neutro com relação ao domínio deve ser instalado no cache de assembly global.

- Você deseja centralizar a manutenção para seu aplicativo aplicando a política do Publicador, o que significa que o assembly deve ser instalado no cache de assembly global.

Se você for um desenvolvedor de software livre e quiser os benefícios de identidade de um assembly de nome forte, considere a verificação da chave privada associada a um assembly para o sistema de controle do código-fonte.

## <a name="see-also"></a>Confira também

- [Cache de assembly global](../../framework/app-domains/gac.md)
- [Como assinar um assembly com um nome forte](sign-strong-name.md)
- [Sn. exe (ferramenta Strong Name)](../../framework/tools/sn-exe-strong-name-tool.md)
- [Criar e usar assemblies com nome forte](create-use-strong-named.md)
