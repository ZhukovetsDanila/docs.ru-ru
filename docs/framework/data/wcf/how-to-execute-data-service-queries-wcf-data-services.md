---
title: Как выполнить Выполнение запросов к службе данных (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- querying the data service [WCF Data Services]
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: 62997821-e0c6-4c4d-9fb7-1273fb5e5d18
ms.openlocfilehash: aac0e4c71ae2752d4f56ae5eadb5f0a8d381d5fe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623291"
---
# <a name="how-to-execute-data-service-queries-wcf-data-services"></a>Как выполнить Выполнение запросов к службе данных (службы данных WCF)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют выполнять запросы к службе данных из клиентского приложения на основе .NET Framework с использованием сформированных клиентских классов службы данных. Выполнять запросы можно одним из следующих способов.  
  
-   Выполнение запроса LINQ к именованному объекту <xref:System.Data.Services.Client.DataServiceQuery%601>, который получен из контекста <xref:System.Data.Services.Client.DataServiceContext>, сформированного программой `Add Data Service Reference`.  
  
-   Неявное перечисление именованного объекта <xref:System.Data.Services.Client.DataServiceQuery%601>, который получен из контекста <xref:System.Data.Services.Client.DataServiceContext>, сформированного программой `Add Data Service Reference`.  
  
-   Явный вызов метода <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> с объектом <xref:System.Data.Services.Client.DataServiceQuery%601> или метода <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> для асинхронного выполнения.  
  
 Дополнительные сведения см. в разделе [запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и клиентские классы данных создаются при завершении [краткое руководство по службам данных WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Следующий пример показывает, как определить и выполнить запрос LINQ, возвращающий все сущности `Customers` в службе данных Northwind.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomersLinq](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getallcustomerslinq)]
 [!code-vb[Astoria Northwind Client#GetAllCustomersLinq](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getallcustomerslinq)]  
  
## <a name="example"></a>Пример  
 Следующий пример показывает, как использовать контекст, сформированный программой `Add Data Service Reference`, для неявного выполнения запроса, возвращающего все сущности `Customers` в службе данных Northwind. URI запрашиваемого набора сущностей `Customers` автоматически определяется контекстом. Запрос выполняется неявно при запуске перечисления.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getallcustomers)]
 [!code-vb[Astoria Northwind Client#GetAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getallcustomers)]  
  
## <a name="example"></a>Пример  
 Следующий пример показывает, как использовать контекст <xref:System.Data.Services.Client.DataServiceContext> для явного выполнения запроса, который возвращает все сущности `Customers` в службе данных Northwind.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomersExplicit](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getallcustomersexplicit)]
 [!code-vb[Astoria Northwind Client#GetAllCustomersExplicit](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getallcustomersexplicit)]  
  
## <a name="see-also"></a>См. также
- [Практическое руководство. Добавление параметров запроса к запросу службы данных](../../../../docs/framework/data/wcf/how-to-add-query-options-to-a-data-service-query-wcf-data-services.md)
