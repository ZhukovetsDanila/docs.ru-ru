---
title: Распределенные транзакции Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 8e7530621254881402570b59b47a22052b40f2b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713254"
---
# <a name="oracle-distributed-transactions"></a>Распределенные транзакции Oracle
Объект <xref:System.Data.OracleClient.OracleConnection> автоматически прикрепляется к существующей распределенной транзакции, если он определяет, что транзакция активна. Автоматическое прикрепление к транзакции происходит при открытии соединения или его получении из пула соединений. Автоматическое прикрепление к существующим транзакциям можно отменить, задав  
  
```  
Enlist=false  
```  
  
 в качестве параметра строки соединения для <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="see-also"></a>См. также
- [Oracle и ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
