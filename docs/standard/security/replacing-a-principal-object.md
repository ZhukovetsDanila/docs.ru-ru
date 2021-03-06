---
title: Замена объекта Principal
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET Framework], replacing principal objects
- security [.NET Framework], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5193756861f407315ec82e4419f1d04495c7dd2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606037"
---
# <a name="replacing-a-principal-object"></a>Замена объекта Principal
Приложения, предоставляющие службы проверки подлинности, должны иметь возможность заменять объект **Principal** (<xref:System.Security.Principal.IPrincipal>) для данного потока. Более того, система безопасности должна защищать возможность замены объектов **Principal** , так как злонамеренно подключенный неправильный **Principal** является угрозой безопасности приложения, предоставляя неверное удостоверение или роль. Таким образом, приложениям, которым требуется возможность замены объектов **Principal** , должен быть предоставлен объект <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> для элемента управления "Участник". (Обратите внимание, что это разрешение не требуется для выполнения проверок безопасности на основе ролей или для создания объектов **Principal** .)  
  
 Текущий объект **Principal** можно заменить, выполнив следующие задачи.  
  
1.  Создайте замещающий объект **Principal** и связанный объект **Identity** (удостоверение).  
  
2.  Подключите новый объект **Principal** к контексту вызова.  
  
## <a name="example"></a>Пример  
 В следующем примере показывается, как создать универсальный объект Principal и использовать его для задания участника потока.  
  
 [!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
 [!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>
- [Объекты Principal и Identity](../../../docs/standard/security/principal-and-identity-objects.md)
