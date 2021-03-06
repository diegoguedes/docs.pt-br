---
title: Ferramentas do .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- command line, .NET Framework tools
- .NET Framework, tools
- tools [.NET Framework]
- running .NET Framework tools
ms.assetid: a2ca532d-91f7-426a-9303-417c2ee1247c
ms.openlocfilehash: 60a9cb241f289cacc7437174f112114e843aca47
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645561"
---
# <a name="net-framework-tools"></a>Ferramentas do .NET Framework

A ferramentas do .NET Framework facilitam a criação, a implantação e o gerenciamento de aplicativos e componentes com o .NET Framework como destino.

A maioria das ferramentas do .NET Framework descritas nesta seção é instalada automaticamente com o Visual Studio. Para baixar o Visual Studio, visite a página [Downloads do Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).

Você pode executar todas as ferramentas da linha de comando, com exceção do Assembly Cache Viewer *(Shfusion.dll).* Você deve acessar *Shfusion.dll* do File Explorer.
  
A melhor maneira de executar as ferramentas de linha de comando é usando o Prompt de Comando do Desenvolvedor do Visual Studio. Esses utilitários permitem executar facilmente as ferramentas, sem navegar até a pasta de instalação. Para obter mais informações, consulte [Prompts de Comando](developer-command-prompt-for-vs.md).

> [!NOTE]
> Algumas ferramentas são específicas para computadores 32 ou 64 bits. Não se esqueça de executar a versão apropriada da ferramenta para o computador.

## <a name="in-this-section"></a>Nesta seção

- [Al.exe (Linker de Montagem)](al-exe-assembly-linker.md)  
Gera um arquivo que tem um manifesto de assembly com base em módulos ou arquivos de recurso.

- [Aximp.exe (Windows Forms ActiveX Control Importer)](aximp-exe-windows-forms-activex-control-importer.md)  
Converte definições de tipo em uma biblioteca de tipos COM para um controle ActiveX em um controle do Windows Forms.

- [Caspol.exe (Ferramenta de Política de Segurança de Acesso de Código)](caspol-exe-code-access-security-policy-tool.md)  
Permite exibir e configurar a política de segurança para o nível de política do computador, o nível de política do usuário e o nível de política da empresa. No .NET Framework 4 e posterior, essa ferramenta não afeta a política cas (code `true`access security, segurança de acesso ao código) a menos que o [ \<elemento legacyCasPolicy>](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) esteja definido como . Para saber mais, confira [Alterações de segurança](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).

- [Cert2spc.exe (Ferramenta de teste de certificado de editor de software)](cert2spc-exe-software-publisher-certificate-test-tool.md)  
Cria um SPC (Software Publisher's Certificate) de um ou mais certificados X.509. Essa ferramenta destina-se apenas a testes.

- [Certmgr.exe (Ferramenta do Gerenciador de Certificados)](certmgr-exe-certificate-manager-tool.md)  
Gerencia certificados, CTLs (listas de certificados confiáveis) e CRLs (listas de certificados revogados).

- [Clrver.exe (Ferramenta de Versão CLR)](clrver-exe-clr-version-tool.md)  
Relata todas as versões instaladas do tempo de execução do idioma comum (CLR) no computador.

- [Comandos](developer-command-prompt-for-vs.md)  
Permite que você use ferramentas .NET Framework mais facilmente. Trata-se de um prompt de comando que define variáveis de ambiente específicas automaticamente.

- [CorFlags.exe (Ferramenta de conversão CorFlags)](corflags-exe-corflags-conversion-tool.md)  
Permite configurar a seção CorFlags do cabeçalho de uma imagem PE.

- [Fuslogvw.exe (Visualizador de log de vinculação de montagem)](fuslogvw-exe-assembly-binding-log-viewer.md)  
Exibe informações sobre associações de assembly para ajudar a diagnosticar por que o .NET Framework não pode localizar um assembly no tempo de execução.

- [Gacutil.exe (Ferramenta global de cache de montagem)](gacutil-exe-gac-tool.md)  
Permite exibir e manipular o conteúdo do cache de assembly global e o cache de download.

- [Ilasm.exe (Montador il)](ilasm-exe-il-assembler.md)  
Gera um arquivo PE com base em IL. É possível executar o executável resultante para determinar se o IL é realizado conforme esperado.

- [Ildasm.exe (Il Desmontador)](ildasm-exe-il-disassembler.md)  
Utiliza um arquivo PE que contém o código IL e cria um arquivo de texto que pode ser inserido no IL Assembler (Ilasm.exe).

- [Installutil.exe (Ferramenta instalador)](installutil-exe-installer-tool.md)  
Permite instalar e desinstalar recursos de servidor executando os componentes de instalador em um assembly especificado. (Funciona com classes no namespace <xref:System.Configuration.Install>.)

- [Lc.exe (Compilador de Licença)](lc-exe-license-compiler.md)  
Lê arquivos de texto que contêm informações de licenciamento e produz um arquivo *.licenses* que pode ser incorporado em um idioma comum executável em tempo de execução como um recurso.

- [Mage.exe (Ferramenta de Geração e Edição de Manifesto)](mage-exe-manifest-generation-and-editing-tool.md)  
Permite criar, editar e assinar manifestos de aplicativo e implantação. Como uma ferramenta de linha de comando, *Mage.exe* pode ser executado com base tanto em scripts de lote quanto em aplicativos com base no Windows, inclusive aplicativos do ASP.NET.

- [MageUI.exe (Ferramenta de Geração e Edição de Manifesto, Cliente Gráfico)](mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)  
Dá suporte à mesma funcionalidade que a ferramenta de linha de comando Mage.exe, mas usa uma interface do usuário (UI) com base no Windows. Suporta a mesma funcionalidade da ferramenta de linha de comando *Mage.exe,* mas usa uma interface de usuário baseada no Windows (UI).

- [MDbg.exe (.NET Framework Command-Line Debugger)](mdbg-exe.md)  
Ajuda fornecedores de ferramentas e desenvolvedores de aplicativos na localização e na correção de bugs em programas com o Common Language Runtime do .NET Framework como destino. Essa ferramenta usa a API de depuração do runtime para fornecer serviços de depuração.

- [Mgmtclassgen.exe (Management Strongly Typed Class Generator)](mgmtclassgen-exe.md)  
Permite gerar uma classe gerenciada Early Bound para uma classe WMI (Windows Management Instrumentation) especificada.

- [Mpgo.exe (Ferramenta de otimização guiada por perfil gerenciado)](mpgo-exe-managed-profile-guided-optimization-tool.md)  
Permite ajustar assemblies de imagem nativa que usam cenários de usuário final comuns. Mpgo.exe permite a geração e o consumo dos dados de perfil para assemblies de aplicativo de imagem nativa (não assemblies do .NET Framework) que usam os cenários de treinamento selecionados pelo desenvolvedor de aplicativos.

- [Ngen.exe (Gerador de Imagem Nativa)](ngen-exe-native-image-generator.md)  
Melhora o desempenho de aplicativos gerenciados por meio do uso de imagens nativas (arquivos contendo o código do computador específico do processador compilado). O runtime pode usar imagens nativas do cache em vez de usar o compilador JIT (Just-In-Time) para compilar o assembly original.

- [Peverify.exe (ferramenta PEVerify)](peverify-exe-peverify-tool.md)  
Ajuda a verificar se o código MSIL (Microsoft intermediate language) e os metadados associados atendem aos requisitos de segurança de tipo.

- [Regasm.exe (Ferramenta de Registro de Montagem)](regasm-exe-assembly-registration-tool.md)  
Lê os metadados dentro de um assembly e adiciona as entradas necessárias ao Registro. Isso permite que clientes COM sejam exibidos como classes do .NET Framework.

- [Regsvcs.exe (.NET Services Installation Tool)](regsvcs-exe-net-services-installation-tool.md)  
Carrega e registra um assembly, gera e instala uma biblioteca de tipos em um aplicativo COM+ versão 1.0 especificado, além de configurar serviços adicionados programaticamente a uma classe.

- [Resgen.exe (Gerador de arquivos de recursos)](resgen-exe-resource-file-generator.md)  
Converte arquivos de texto *(.txt* ou *.restext)* e arquivos de formato de recurso baseados em XML *(.resx)* em arquivos binários de tempo de execução de linguagem comum *(.resources)* que podem ser incorporados em um executável binário em tempo de execução ou compilados em conjuntos de satélites.

- [SecAnnotate.exe (.NET Security Anotator Tool)](secannotate-exe-net-security-annotator-tool.md)  
Identifica as partes `SecurityCritical` e `SecuritySafeCritical` de um assembly.

- [SignTool.exe (Ferramenta de sinais)](signtool-exe.md)  
Assina digitalmente arquivos, verifica assinaturas em arquivos e aplica carimbos de data/hora em arquivos.

- [Sn.exe (Ferramenta de Nome Forte)](sn-exe-strong-name-tool.md)  
Ajuda a criar assemblies com nomes fortes. Esta ferramenta oferece opções para o gerenciamento de chaves, geração de assinaturas e verificação de assinaturas.

- [SOS.dll (Extensão de depuração do SOS)](sos-dll-sos-debugging-extension.md)  
Ajuda a depurar programas gerenciados no depurador WinDbg.exe e no Visual Studio fornecendo informações sobre o ambiente interno do CLR (Common Language Runtime).

- [SqlMetal.exe (Ferramenta de Geração de Código)](sqlmetal-exe-code-generation-tool.md)  
Gera o código e o mapeamento para o componente LINQ to SQL do .NET Framework.

- [Storeadm.exe (Ferramenta de armazenamento isolado)](storeadm-exe-isolated-storage-tool.md)  
Gerencia o armazenamento isolado; dá opções para listar os repositórios do usuário e excluí-los.

- [Tlbexp.exe (Tipo De Biblioteca Exportadora)](tlbexp-exe-type-library-exporter.md)  
Gera uma biblioteca de tipos que descreve os tipos definidos em um assembly do Common Language Runtime.

- [Tlbimp.exe (Importador de Biblioteca sinuosa)](tlbimp-exe-type-library-importer.md)  
Converte as definições de tipo encontradas em uma biblioteca de tipos COM em definições equivalentes em um assembly do Common Language Runtime.

- [Winmdexp.exe (Ferramenta de exportação de metadados do Windows Runtime)](winmdexp-exe-windows-runtime-metadata-export-tool.md)  
Exporta um conjunto .NET Framework que é compilado como um arquivo *.winmdobj* em um componente do Windows Runtime, que é embalado como um arquivo *.winmd* que contém metadados do Windows Runtime e informações de implementação.

- [Winres.exe (Editor de recursos do Windows Forms)](winres-exe-windows-forms-resource-editor.md)  
Ajuda você a localizar os recursos de interface do usuário (UI)*(arquivos .resx* ou *.resources)* que são usados pelo Windows Forms. É possível converter cadeias de caracteres e, em seguida, dimensionar, mover e ocultar controles para acomodar as cadeias de caracteres localizadas.

## <a name="related-sections"></a>Seções relacionadas

- [ferramentas WPF](https://docs.microsoft.com/previous-versions/ms742404(v=vs.110))  
Inclui ferramentas como a Conformidade do isXPS (isXPS.exe) e ferramentas de criação de perfil de desempenho.

- [Ferramentas do Windows Communication Foundation](../wcf/tools.md)  
Inclui ferramentas que facilitam a criação, a implantação e o gerenciamento de aplicativos do WCF (Windows Communication Foundation).
