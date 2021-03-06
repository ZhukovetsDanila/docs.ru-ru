---
title: Подписывание хранимых процедур в SQL Server
ms.date: 01/05/2018
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
ms.openlocfilehash: da7b21d725d301006288245c940e4367c3ce8568
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606826"
---
# <a name="signing-stored-procedures-in-sql-server"></a>Подписывание хранимых процедур в SQL Server
 Цифровая сигнатура представляет собой хэш-код данных, зашифрованную при помощи закрытого ключа лица, ставящего свою сигнатуру. Закрытый ключ обеспечивает уникальность цифровой сигнатуры его владельцу. Можно подписывать хранимые процедуры, функции (за исключением встроенных функций с табличным), триггеры и сборки.  
  
 Хранимую процедуру можно подписать сертификатом или асимметричным ключом. Эта возможность предназначена для сценариев, в которых разрешения не могут наследоваться по цепочке владения или если цепочка владения разорвана, например в динамическом SQL. Затем можно создать пользователя, сопоставленного с сертификатом, предоставление сертификата пользователя разрешений на объекты, которые требуется доступ к хранимой процедуре.  

 Можно также создать имя входа сопоставляется один и тот же сертификат и затем предоставить все необходимые разрешения уровня сервера для этого имени входа или добавьте имя входа в одну или несколько предопределенных ролей сервера. Это позволяет избежать включения `TRUSTWORTHY` базы данных параметра для сценариев, в которых требуются разрешения более высокого уровня.  
  
 При выполнении хранимой процедуры SQL Server объединяет разрешения пользователя сертификата и/или имя входа с разрешениями вызывающей стороны. В отличие от `EXECUTE AS` предложение, он не меняет контекст выполнения процедуры. Встроенные функции, которые возвращают имя входа и имена пользователей, возвращают имя вызывающей стороны, а не имя пользователя сертификата.  
  
## <a name="creating-certificates"></a>Создание сертификатов  
 При регистрации хранимой процедуры с помощью сертификата или асимметричного ключа, сводка данных, состоящая из зашифрованного хэш-код хранимой процедуры, а также execute — от имени пользователя, создается с помощью закрытого ключа. Во время выполнения сводка данных расшифровывается открытым ключом и сравнивается с хэш-кодом хранимой процедуры. Изменение execute — как пользователь сделает недействительным хэш-значения, чтобы цифровая подпись не соответствует. Изменение хранимой процедуры удаляет подпись полностью, который исключает теми, кто не имеет доступа к закрытому ключу изменять код хранимой процедуры. В любом случае следует подписывать процедуру каждый раз при изменении кода или execute — от имени пользователя.  
  
 Существует два действия, необходимые, участвующих в Подписание модулей:  
  
1.  Создание сертификата с использованием инструкции Transact-SQL `CREATE CERTIFICATE [certificateName]`. Эта инструкция имеет несколько параметров для настройки даты начала и даты окончания, а также пароля. Дата окончания срока действия по умолчанию — один год.  
  
1.  Подписание процедуры при помощи сертификата с использованием инструкции Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]`.  

После подписания модуля, одного или нескольких участников должна быть создана для хранения дополнительных разрешений, которые должны быть связаны с сертификатом.  

Если модуль должен дополнительные разрешения уровня базы данных:  
  
1.  Создание пользователя базы данных, связанного с этим сертификатом, с использованием инструкции Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]`. Этот пользователь существует только в базе данных и не связан с именем входа, если имя входа также должна быть создана из этой же сертификата.  
  
1.  Предоставление пользователю сертификата необходимых разрешений на уровне базы данных.  
  
Если модуль должен дополнительные разрешения уровня сервера:  
  
1.  Скопируйте сертификат `master` базы данных.  
 
1.  Создайте имя входа, связанное с этим сертификатом, с помощью Transact-SQL `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` инструкции.  
  
1.  Предоставьте имя входа сертификата необходимые разрешения на уровне сервера.  
  
> [!NOTE]  
>  Сертификат не может предоставлять разрешения пользователю, у которого разрешения были отменены инструкцией DENY. DENY имеет преимущество над GRANT, предотвращая тем самым наследование вызывающей стороной разрешений, предоставленных пользователю сертификата.  
  
## <a name="external-resources"></a>Внешние ресурсы  
 Дополнительные сведения см. в следующих ресурсах.  
  
|Ресурс|Описание|  
|--------------|-----------------|  
|[Подписание модулей](https://go.microsoft.com/fwlink/?LinkId=98590) в электронной документации по SQL Server|Описывает подписывание модулей, демонстрирует образец сценария и содержит ссылки на соответствующие разделы по языку Transact-SQL.|  
|[Подписывание хранимых процедур с помощью сертификата](/sql/relational-databases/tutorial-signing-stored-procedures-with-a-certificate) в электронной документации по SQL Server|Предоставляет учебник для подписания хранимой процедуры с помощью сертификата.|  
  
## <a name="see-also"></a>См. также
- [Защита приложений ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [Общие сведения о безопасности SQL Server](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)
- [Сценарии безопасности приложений в SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [Управление разрешениями с использованием хранимых процедур в SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)
- [Написание безопасного динамического кода SQL в SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)
- [Настройка разрешений с олицетворением в SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)
- [Изменение данных с помощью хранимых процедур](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
