---
title: "Объект My.Forms | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "My.Forms"
  - "My.MyProject.Forms"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Forms - объект"
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Объект My.Forms
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Предоставляет свойства для доступа к экземпляру каждой формы Windows Forms, объявленной в текущем проекте.  
  
## Заметки  
 Объект `My.Forms` предоставляет экземпляр каждой формы в текущем проекте.  Имя свойства совпадает с именем формы, к которой обращается свойство.  Сведения о добавлении форм в проект содержатся в разделе [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/ru-ru/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
 Доступ к форме, предоставляемой объектом `My.Forms`, можно получить с помощью имени формы без квалификации.  Поскольку имя свойства совпадает с именем типа формы, это позволяет получить доступ к форме таким же образом, как если бы она имела экземпляр по умолчанию.  Например, запись `My.Forms.Form1.Show` эквивалентна записи `Form1.Show`.  
  
 Объект `My.Forms` предоставляет только формы, связанные с текущим проектом.  Он не обеспечивает доступа к формам, объявленным в присоединенных библиотеках DLL.  Для доступа к форме, предоставленной библиотекой DLL, необходимо использовать полное имя формы, которое формируется следующим образом: *ИмяDLL*.*ИмяФормы*.  
  
 Свойство <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> можно использовать для получения коллекции открытых форм приложения.  
  
 Объект и его свойства доступны только для приложений Windows.  
  
## Свойства  
 Каждое свойство объекта `My.Forms` предоставляет доступ к экземпляру формы в текущем проекте.  Имя свойства совпадает с именем формы, к которой осуществляется доступ, а тип свойства совпадает с типом формы.  
  
> [!NOTE]
>  Если имеется конфликт имен, имя свойства для доступа к форме формируется следующим образом: *КорневоеПространствоИмен*\_*ПространствоИмен* \_ *ИмяФормы*.  Например, рассмотрим две формы с именем `Form1.` Если одна из этих форм находится в корневом пространстве имен `WindowsApplication1` и в пространстве имен `Namespace1`, доступ к этой форме будет осуществляться с помощью `My.Forms.WindowsApplication1_Namespace1_Form1`.  
  
 Объект `My.Forms` предоставляет доступ к экземпляру приложения главной формы, созданной при запуске.  Для всех других форм объект `My.Forms` создает новый экземпляр формы при доступе к нему или при его сохранении.  Последующие попытки доступа к этому свойству возвращают этот экземпляр формы.  
  
 Можно уничтожить форму путем назначения свойству этой формы значения `Nothing`.  Установщик свойства вызывает метод формы <xref:System.Windows.Forms.Form.Close%2A>, а затем назначает `Nothing` для хранимого значения.  Если назначить свойству любое значение, отличное от `Nothing`, установщик сгенерирует исключение <xref:System.ArgumentException>.  
  
 Чтобы проверить, хранит ли свойство объекта `My.Forms` экземпляр формы, воспользуйтесь оператором `Is` или `IsNot`.  Эти операторы можно использовать для проверки того, имеет ли свойство значение `Nothing`.  
  
> [!NOTE]
>  Обычно оператор `Is` или `IsNot` должен прочитать значение свойства для выполнения сравнения.  Однако если свойство в настоящее время имеет значение `Nothing`, свойство создает новый экземпляр формы, а затем возвращает этот экземпляр.  Компилятор Visual Basic по\-разному обрабатывает свойства объекта `My.Forms` и позволяет операторам `Is` или `IsNot` проверить состояние свойства без изменения его значения.  
  
## Пример  
 В данном примере изменяется название исходной формы `SidebarMenu`.  
  
 [!CODE [VbVbalrMyForms#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyForms#2)]  
  
 Чтобы этот пример работал, проект должен иметь форму с именем `SidebarMenu`.  Дополнительные сведения см. в разделе [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/ru-ru/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
 Этот код будет работать только в проекте приложения Windows.  
  
## Требования  
  
### Доступность по типу проекта  
  
|||  
|-|-|  
|Тип проекта|Доступность|  
|Приложение Windows|**Да**|  
|Библиотека классов|Нет|  
|Консольное приложение|Нет|  
|Библиотека элементов управления Windows|Нет|  
|Библиотека веб\-элементов управления|Нет|  
|Служба Windows|Нет|  
|Веб\-узел|Нет|  
  
## См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>   
 <xref:System.Windows.Forms.Form>   
 <xref:System.Windows.Forms.Form.Close%2A>   
 [Объекты](../../../visual-basic/language-reference/objects/index.md)   
 [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/ru-ru/3d7bb25f-fd90-47cf-9378-fa0d764686c1)   
 [Оператор Is](../../../visual-basic/language-reference/operators/is-operator.md)   
 [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Доступ к формам приложения](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)