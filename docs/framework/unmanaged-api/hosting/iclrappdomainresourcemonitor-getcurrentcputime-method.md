---
title: Método ICLRAppDomainResourceMonitor::GetCurrentCpuTime
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
ms.openlocfilehash: b411190ff36410c1d293f1e48b31975be8a13aee
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616028"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a>Método ICLRAppDomainResourceMonitor::GetCurrentCpuTime
Obtém o tempo total do processador que foi usado por todos os threads durante a execução no domínio do aplicativo atual, desde que o domínio do aplicativo foi criado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `dwAppDomainId`  
 no A ID do domínio do aplicativo solicitado.  
  
 `pMilliseconds`  
 fora Um ponteiro para o tempo total do processador que foi usado por todos os threads durante a execução no domínio do aplicativo atual desde que o domínio do aplicativo foi criado. Esse parâmetro pode ser `null`.  
  
## <a name="return-value"></a>Valor retornado  
  
|HRESULT|Descrição|  
|-------------|-----------------|  
|S_OK|O método foi concluído com êxito.|  
|COR_E_APPDOMAINUNLOADED|O domínio do aplicativo foi descarregado ou não existe.|  
|E_FAIL|O monitoramento de recursos de domínio do aplicativo não está habilitado.<br /><br /> – ou –<br /><br /> Todas as outras falhas.|  
  
## <a name="remarks"></a>Comentários  
 Esse método é o equivalente não gerenciado da propriedade gerenciada <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MetaHost. h  
  
 **Biblioteca:** Incluído como um recurso em MSCorEE. dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Veja também

- [Interface ICLRAppDomainResourceMonitor](iclrappdomainresourcemonitor-interface.md)
- [Interfaces de hospedagem](hosting-interfaces.md)
- [Monitoramento de recursos de domínio do aplicativo](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Hospedagem](index.md)
