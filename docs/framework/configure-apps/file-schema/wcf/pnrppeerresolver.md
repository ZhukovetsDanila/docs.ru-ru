---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: f98c358cc9891e9d7223d280fc8e50c19aad9759
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260659"
---
# <a name="pnrppeerresolver"></a>\<pnrpPeerResolver >
Задает использование распознавателя протокола PNRP (протокола однорангового разрешения имен) в качестве распознавателя. Этот элемент является необязательным, поскольку протокол PNRP является распознавателем по умолчанию.  
  
 \<system.serviceModel>  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<pnrpResolver>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|resolverType|Строка, указывающая распознаватель для использования. Этот атрибут является необязательным. Если значение не задано или равно пустой строке, используется протокол PNRP.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<Привязка >](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## <a name="example"></a>Пример  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Привязки](../../../../../docs/framework/wcf/bindings.md)
- [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [Одноранговые распознаватели](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
