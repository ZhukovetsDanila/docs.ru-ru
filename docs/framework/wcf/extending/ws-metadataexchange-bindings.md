---
title: Привязки WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 03e6e6d5ee7e69b397acd0f51b8037f02c1804ec
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2018
ms.locfileid: "53767352"
---
# <a name="ws-metadataexchange-bindings"></a>Привязки WS-MetadataExchange
В этом разделе описано, как создавать привязки обмена метаданными по умолчанию для различных транспортов.  
  
## <a name="the-default-bindings"></a>Привязки по умолчанию  
  
|Имя привязки по умолчанию|Создание привязки|  
|--------------------------|------------------------------------|  
|mexHttpBinding|Привязка <xref:System.ServiceModel.WSHttpBinding> с отключенной безопасностью транспортного уровня.|  
|mexHttpsBinding|Привязка <xref:System.ServiceModel.WSHttpBinding> с поддержкой безопасности транспортного уровня.|  
|mexNamedPipeBinding|Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> и значениями по умолчанию.|  
|mexTcpBinding|Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.TcpTransportBindingElement> и значениями по умолчанию.|
