---
title: Извлечение сведений о настройке из домена приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- AppDomainSetup object
- retrieving setup information
- application domains, retrieving setup information
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c5b43258b3ce501d1302c31a70f51341d3a84d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588042"
---
# <a name="retrieving-setup-information-from-an-application-domain"></a>Извлечение сведений о настройке из домена приложения
Каждый экземпляр домена приложения содержит свойства и сведения <xref:System.AppDomainSetup>. Сведения о настройке можно получить из домена приложения с помощью класса <xref:System.AppDomain?displayProperty=nameWithType>. Этот класс предоставляет несколько членов, извлекающих сведения конфигурации домена приложения.  
  
 Кроме того, для получения сведений о настройке домена приложения можно выполнить запрос объекта **AppDomainSetup**, который был передан в домен при его создании.  
  
 В следующем примере создается домен приложения и выполняется вывод значений нескольких его членов на консоль.  
  
 [!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)]
 [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)]
 [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]  
  
 В следующем примере для домена приложения задаются и извлекаются сведения о настройке. Обратите внимание, что `AppDomain.SetupInformation.ApplicationBase` получает сведения о конфигурации.  
  
 [!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)]
 [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)]
 [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]  
  
## <a name="see-also"></a>См. также
- [Программирование с использованием доменов приложений](application-domains.md#programming-with-application-domains)
- [Использование доменов приложений](../../../docs/framework/app-domains/use.md)
