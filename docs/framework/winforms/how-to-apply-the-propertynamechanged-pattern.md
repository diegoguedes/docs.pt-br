---
title: 'Como: aplicar o padrão PropertyNameChanged'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 01afa713e97206ea192ba55dc2affad20163f872
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665256"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a>Como: aplicar o padrão PropertyNameChanged
O exemplo de código a seguir demonstra como aplicar a *PropertyName*Changed padrão para um controle personalizado. Aplica esse padrão quando você implementa controles personalizados que são usados com o mecanismo de associação de dados de formulários do Windows.  
  
## <a name="example"></a>Exemplo  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Para compilar o exemplo de código anterior:  
  
- Cole o código em um arquivo de código vazio. Você deve usar o controle personalizado em um formulário do Windows que contenha um `Main` método.  
  
## <a name="see-also"></a>Consulte também

- [Como: Implementar a Interface INotifyPropertyChanged](how-to-implement-the-inotifypropertychanged-interface.md)
- [Notificação de alteração na vinculação de dados dos Windows Forms](change-notification-in-windows-forms-data-binding.md)
- [Associação de dados do Windows Forms](windows-forms-data-binding.md)
