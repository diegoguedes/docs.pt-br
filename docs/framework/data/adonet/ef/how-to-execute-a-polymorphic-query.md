---
title: 'Como: executar uma consulta polimorfo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 49e0a6b44af0729959fabf6278cc6d8ecf37a16b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251506"
---
# <a name="how-to-execute-a-polymorphic-query"></a>Como: executar uma consulta polimorfo

Este tópico mostra como executar uma [!INCLUDE[esql](../../../../../includes/esql-md.md)] consulta polimórfica usando o operador [OfType](./language-reference/oftype-entity-sql.md) .

### <a name="to-run-the-code-in-this-example"></a>Para executar o código nesse exemplo

1. Adicione o [modelo escolar](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) ao seu projeto e configure seu projeto para usar o Entity Framework. Para obter mais informações, confira [Como: Use o assistente](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))de modelo de dados de entidade.

2. Na página de código do seu aplicativo, adicione as seguintes instruções `using` (`Imports` no Visual Basic):

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. Modifique o modelo conceitual para ter uma herança de tabela por hierarquia seguindo as etapas descritas [em Walkthrough: Mapeamento de herança – tabela por hierarquia](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).

## <a name="example"></a>Exemplo

O seguinte exemplo usa um operador de OFTYPE para obter e exibir uma coleção somente de `OnsiteCourses` de uma coleção de `Courses`.

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a>Consulte também

- [Provedor EntityClient para Entity Framework](entityclient-provider-for-the-entity-framework.md)
- [Entity SQL Language](./language-reference/entity-sql-language.md) (Linguagem SQL de entidade)
