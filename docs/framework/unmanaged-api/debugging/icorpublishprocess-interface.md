---
title: Interface ICorPublishProcess
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
ms.openlocfilehash: 8d958e949612b502ab218f5c6b75779174d34e19
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421079"
---
# <a name="icorpublishprocess-interface"></a>Interface ICorPublishProcess
Fornece métodos que acessam informações a serem exibidas sobre um processo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descrição|  
|------------|-----------------|  
|[Método EnumAppDomains](icorpublishprocess-enumappdomains-method.md)|Obtém uma instância de [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) que contém os domínios de aplicativo no processo referenciado por isso `ICorPublishProcess` .|  
|[Método GetDisplayName](icorpublishprocess-getdisplayname-method.md)|Obtém o caminho completo do executável para o processo referenciado por isso `ICorPublishProcess` .|  
|[Método GetProcessID](icorpublishprocess-getprocessid-method.md)|Obtém o identificador do sistema operacional para o processo referenciado por isso `ICorPublishProcess` .|  
|[Método IsManaged](icorpublishprocess-ismanaged-method.md)|Obtém um valor que indica se o processo referenciado por isso `ICorPublishProcess` é conhecido por estar executando código gerenciado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Veja também

- [Depurando interfaces](debugging-interfaces.md)
- [Coclass CorpubPublish](corpubpublish-coclass.md)
