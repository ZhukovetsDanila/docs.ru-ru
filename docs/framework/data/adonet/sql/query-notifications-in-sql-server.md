---
title: Уведомления запросов в SQL Server
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 166471658ccd1ef48db2ac1647f74ea696f3263d
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092297"
---
# <a name="query-notifications-in-sql-server"></a>Уведомления запросов в SQL Server
С помощью уведомлений о запросах на основе инфраструктуры компонента Service Broker приложения могут получать извещения об изменениях данных. Эта функция особенно полезна для приложений, которые предоставляют кэш данных из базы данных (например, для веб-приложений), и которым требуются уведомления об изменении исходных данных.  
  
 Существует три способа реализации уведомлений о запросах с помощью ADO.NET.  
  
1.  Низкоуровневую реализацию обеспечивает класс `SqlNotificationRequest`, который предоставляет функциональность на стороне сервера, позволяя выполнить команду с запросом на уведомления.  
  
2.  Высокоуровневая реализация обеспечивается классом `SqlDependency`, который обеспечивает высокоуровневую абстракцию работы с уведомлениями между исходным приложением и SQL Server, позволяя определять изменения на сервере с помощью зависимости. В большинстве случаев это самый простой и самый эффективный способ задействовать возможности уведомления SQL Server в управляемых клиентских приложениях с помощью поставщика данных .NET Framework для SQL Server.  
  
3.  Кроме того, в веб-приложениях, построенных с помощью ASP.NET 2.0 или более поздних версий, можно использовать вспомогательные классы `SqlCacheDependency`.  
  
 Уведомления о запросах используются в приложениях, в которых при изменении данных необходимо обновлять соответствующие данные на экране или в кэше. Microsoft SQL Server позволяет приложениям .NET Framework передавать команды в SQL Server и запрашивать уведомления, если при выполнении одной и той же команды может получиться результирующий набор, отличный от полученного первоначально. Уведомления, создаваемые на сервере, помещаются в очереди для последующей обработки.  
  
 Уведомления можно задать для инструкций SELECT и EXECUTE. При использовании инструкции EXECUTE сервер SQL Server регистрирует уведомление для выполняемой команды, а не самой инструкции EXECUTE. Команда должна соответствовать требованиям, предъявляемым к инструкции SELECT. Если команда, для которой регистрируется уведомление, состоит из нескольких инструкций, компонент Database Engine создает уведомления для каждой из них.  
  
 При разработке приложения нужном надежных доли секунды уведомления об изменении данных, см. подразделы **планирование эффективной стратегии уведомлений о запросах** и **альтернативы запроса Уведомления** в [планирование уведомлений](https://go.microsoft.com/fwlink/?LinkId=211984) раздела в электронной документации по SQL Server. Дополнительные сведения об уведомлениях о запросах и компоненте SQL Server Service Broker см. в указанных ниже разделах электронной документации по SQL Server.  
  
 **Документация по SQL Server**  
  
-   [С помощью уведомлений о запросах](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))  
  
-   [Создание запроса для уведомлений](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
-   [Разработка (компонент Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))  
  
-   [Справочный центр разработчика службы Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
-   [Руководство разработчика (компонент Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="in-this-section"></a>В этом разделе  
 [Включение уведомлений запросов](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)  
 Описывает использование уведомлений о запросах, в том числе требования к их включению и использованию.  
  
 [SqlDependency в приложении ASP.NET](../../../../../docs/framework/data/adonet/sql/sqldependency-in-an-aspnet-app.md)  
 Демонстрирует использование уведомлений о запросах из приложения ASP.NET.  
  
 [Обнаружение изменений с использованием SqlDependency](../../../../../docs/framework/data/adonet/sql/detecting-changes-with-sqldependency.md)  
 Демонстрирует, как определить, когда результаты запроса будут отличаться от полученных первоначально.  
  
 [Выполнение SqlCommand с помощью SqlNotificationRequest](../../../../../docs/framework/data/adonet/sql/sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 Демонстрирует настройку работы с уведомлениями о запросах в объекте <xref:System.Data.SqlClient.SqlCommand>.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 Описывает класс <xref:System.Data.Sql.SqlNotificationRequest> и все его члены.  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 Описывает класс <xref:System.Data.SqlClient.SqlDependency> и все его члены.  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 Описывает класс <xref:System.Web.Caching.SqlCacheDependency> и все его члены.  
  
## <a name="see-also"></a>См. также
- [SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
