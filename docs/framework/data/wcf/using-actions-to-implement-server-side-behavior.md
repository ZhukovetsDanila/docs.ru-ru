---
title: Использование действий для реализации поведения на стороне сервера
ms.date: 03/30/2017
ms.assetid: 11a372db-7168-498b-80d2-9419ff557ba5
ms.openlocfilehash: fdff4f87e0c22baeb92ee844e0dae1fa9bef8302
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092128"
---
# <a name="using-actions-to-implement-server-side-behavior"></a>Использование действий для реализации поведения на стороне сервера

Действия OData предоставляют способ реализации поведения, срабатывающего при получении ресурса из службы OData. Рассмотрим для примера цифровой фильм в качестве ресурса. С цифровым фильмом можно совершить множество различных действий: извлекать, оценивать, комментировать или возвращать. Приведенные варианты являются примерами действий, которые могут выполняться службой данных WCF, управляющей цифровыми фильмами. Действия описываются в ответе OData, содержащим ресурс, для которого может быть вызвано это действие. Если пользователь запрашивает ответ, который представляет цифровой фильм, то ответ, возвращаемый службой данных WCF, содержит сведения о действиях, которые могут быть применены к этому ресурсу. Доступность действия зависит от состояния службы данных или ресурса. Например, цифровой фильм, извлеченный одним пользователем, не может быть извлечен другим пользователем. Для вызова действий клиентам достаточно указать URL-адрес. Например `http://MyServer/MovieService.svc/Movies(6)` будет обозначать определенный цифровой фильм и `http://MyServer/MovieService.svc/Movies(6)/Checkout` вызовет действие фильмом. Действия позволяют применять модель службы, не обращаясь к модели данных. Продолжим рассмотрение примера с фильмом. Например, вы можете разрешить пользователям оценивать фильм, но не предоставлять доступ к данным оценок как к ресурсу. Вы можете реализовать действие оценки, чтобы разрешить пользователям оценивать фильм, при этом у них не будет прямого доступа к данным оценок как к ресурсу.
  
## <a name="implementing-an-action"></a>Реализация действия  
 Для реализации действия службы, необходимо реализовать <xref:System.IServiceProvider>, [IDataServiceActionProvider](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)), и [интерфейса IDataServiceInvokable](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859893(v=vs.103)) интерфейсов. <xref:System.IServiceProvider> позволяет службам данных WCF получить вашу реализацию [IDataServiceActionProvider](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)). [IDataServiceActionProvider](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)) позволяет службам данных WCF для создания, поиска, описания и вызывать действия службы. [Интерфейса IDataServiceInvokable](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859893(v=vs.103)) позволяет вызывать код, который реализует поведение действий службы и получить результаты, если таковые имеются. Помните, что службы данных WCF являются службами с предварительным вызовом, то есть новый экземпляр службы создается при каждом вызове службы.  Удостоверьтесь в том, что при создании службы выполняется только необходимая работа.  
  
### <a name="iserviceprovider"></a>IServiceProvider  
 Интерфейс <xref:System.IServiceProvider> содержит метод <xref:System.IServiceProvider.GetService%2A>. Службы данных WCF вызывают этот метод для получения числа поставщиков служб, включая поставщиков служб метаданных и поставщиков действий служб данных. При запросе поставщика действий службы данных, возвращают вашей [IDataServiceActionProvider](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)) реализации.  
  
### <a name="idataserviceactionprovider"></a>IDataServiceActionProvider  
 [IDataServiceActionProvider](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)) содержит методы, которые позволяют получить сведения о доступных действиях. При реализации [IDataServiceActionProvider](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)) увеличивается метаданных для вашей службы, которая определяется вашей реализацией интерфейса [IDataServiceActionProvider](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)) с действиями и обработки их отправки соответствующим образом.  
  
#### <a name="advertiseserviceaction"></a>AdvertiseServiceAction  
 [AdvertiseServiceAction метод](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859971(v=vs.103)) вызывается, чтобы определить, какие действия доступны для указанного ресурса. Этот метод вызывается только для действий, которые не всегда доступны. Он используется для проверки того, следует ли включать действие в ответ OData, исходя из состояния запрашиваемого ресурса или службы. Способ выполнения этой проверки полностью зависит от вас. Если вычислять доступность затратно, а текущий ресурс находится в веб-канале, можно просто пропустить проверку и объявить о доступности действия. Если текущий ресурс в данный момент возвращается в рамках веб-канала, параметру `inFeed` задается значение `true`.  
  
#### <a name="createinvokable"></a>CreateInvokable  
 [CreateInvokable](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859940(v=vs.103)) вызывается для создания [интерфейса IDataServiceInvokable](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859893(v=vs.103)) , содержащий делегат, инкапсулирующий код, который реализует поведение действия. При этом создается [интерфейса IDataServiceInvokable](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859893(v=vs.103)) экземпляра, но не вызывать действие. У действий службы данных WCF имеются побочные эффекты, они должны выполняться в сочетании с поставщиком обновлений для сохранения этих изменений на диске. [IDataServiceInvokable.Invoke](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859924(v=vs.103)) метод вызывается из SaveChanges() поставщика обновлений, вызывается метод.  
  
#### <a name="getserviceactions"></a>GetServiceActions  
 Этот метод возвращает коллекцию [ServiceAction](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) экземпляры, представляющие все действия, реализованные службой данных WCF. [ServiceAction](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) является представлением метаданных действия, которое включает в себя такие сведения, как имя действия, его параметры и тип его возвращаемого значения.  
  
#### <a name="getserviceactionsbybindingparametertype"></a>GetServiceActionsByBindingParameterType  
 Этот метод возвращает коллекцию всех [ServiceAction](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) экземпляров, которые могут быть привязаны к указанному типу параметра привязки. Другими словами, все [ServiceAction](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)), которые могут выполняться на указанный тип ресурса (также называется типом параметра привязки). Используется, если служба возвращает ресурс, чтобы включить сведения о действиях, которые можно вызвать для этого ресурса. Этот метод должен возвращать только действия, которые могут быть привязаны к указанному типу параметра привязки (а не производным типам). Этот метод вызывается один раз для каждого запроса и каждого типа, а результат его работы кэшируется службами данных WCF.  
  
#### <a name="tryresolveserviceaction"></a>TryResolveServiceAction  
 Этот метод осуществляет поиск указанного [ServiceAction](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) и возвращает `true` Если [ServiceAction](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) найден. Если найден, [ServiceAction](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) возвращается в `serviceAction` `out` параметра.  
  
### <a name="idataserviceinvokable"></a>IDataServiceInvokable  
 Этот интерфейс обеспечивает способ выполнения действия службы данных WCF. При реализации интерфейса IDataServiceInvokable необходимо учесть три вещи.  
  
1.  Отслеживание и, потенциально, маршалинг параметров.  
  
2.  Передача параметров коду, который фактически реализует действие при вызове метода Invoke().  
  
3.  Сохранение результатов работы метода Invoke() с тем, чтобы их можно было получить с помощью метода GetResult().  
  
 Параметры могут передаваться в виде токенов. Это так, потому что можно написать поставщика службы данных, работающего с токенами, которые представляют ресурсы. При реализации такой схемы может потребоваться преобразование (маршалинг) этих токенов в сами ресурсы до их отправки собственно действию. После преобразования параметра он должен находиться в состоянии, допускающем редактирование с тем, чтобы любые изменения ресурса, происходящие при вызове действия, сохранялись и записывались на диск.  
  
 Этому интерфейсу требуется два метода: Invoke и GetResult. Метод Invoke вызывает делегата, который реализует поведение действия, а метод GetResult возвращает результат выполнения действия.  
  
## <a name="invoking-a-wcf-data-service-action"></a>Вызов действия службы данных WCF  
 Действия вызываются с помощью запроса HTTP POST. В URL-адресе указывается ресурс, за которым следует имя действия. Параметры передаются в тексте запроса. Например, при наличии службы MovieService, которая выполняла действие Rate. Для вызова действия Rate в отношении определенного фильма можно использовать следующий URL-адрес:  
  
 `http://MovieServer/MovieService.svc/Movies(1)/Rate`
  
 Movies(1) обозначает фильм, который требуется оценить, а Rate обозначает действие Rate. Само значение оценки будет приведено в тексте HTTP-запроса, как показано в следующем примере:  
  
```  
POST http://MovieServer/MoviesService.svc/Movies(1)/Rate HTTP/1.1   
Content-Type: application/json   
Content-Length: 20   
Host: localhost:15238  
{   
   "rating": 4   
}  
```  
  
> [!WARNING]
> Приведенный выше образец кода будет работать только со службами данных WCF 5.2 и более поздней версии, которые поддерживают облегченный формат JSON. При использовании более ранней версии служб данных WCF необходимо указать подробный тип содержимого json следующим образом: `application/json;odata=verbose`.  
  
 Также можно вызывать действия с помощью клиента служб данных WCF, как показано в следующем фрагменте кода:  
  
```csharp
MoviesModel context = new MoviesModel (new Uri("http://MyServer/MoviesService.svc/"));  
//...  
context.Execute(new Uri("http://MyServer/MoviesService.svc/Movies(1)/Rate"), "POST", new BodyOperationParameter("rating",4) );
```
  
 В приведенном выше фрагменте кода класс `MoviesModel` был сформирован с помощью Visual Studio для добавления ссылки на службу данных WCF.  
  
## <a name="see-also"></a>См. также
- [Службы данных WCF 4.5](../../../../docs/framework/data/wcf/index.md)
- [Определение служб данных WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [Разработка и развертывание служб WCF Data Services](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)
- [Специализированные поставщики служб данных](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md)
