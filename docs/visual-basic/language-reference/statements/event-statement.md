---
title: "Оператор Event | Microsoft Docs"
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
  - "vb.Event"
  - "vb.Custom"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ByRef - ключевое слово, Event - операторы"
  - "ByVal - ключевое слово, Event - операторы"
  - "Custom - ключевое слово"
  - "декларации, события"
  - "объявление событий, синтаксис"
  - "объявление пользовательских событий"
  - "event -ключевое слово [Visual Basic]"
  - "Event - оператор"
  - "события [Visual Basic], пользовательский"
  - "события [Visual Basic], объявление"
  - "Public - ключевое слово, Event - операторы"
  - "WithEvents - ключевое слово, Event - операторы"
ms.assetid: 306ff8ed-74dd-4b6a-bd2f-e91b17474042
caps.latest.revision: 33
caps.handback.revision: 33
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор Event
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Объявляет пользовательское событие.  
  
## Синтаксис  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shared ] [ Shadows ] Event eventname[(parameterlist)] _  
[ Implements implementslist ]  
' -or-  
[ <attrlist> ] [ accessmodifier ] _  
[ Shared ] [ Shadows ] Event eventname As delegatename _  
[ Implements implementslist ]  
' -or-  
 [ <attrlist> ] [ accessmodifier ] _  
[ Shared ] [ Shadows ] Custom Event eventname As delegatename _  
[ Implements implementslist ]  
   [ <attrlist> ] AddHandler(ByVal value As delegatename)  
      [ statements ]  
   End AddHandler  
   [ <attrlist> ] RemoveHandler(ByVal value As delegatename)  
      [ statements ]  
   End RemoveHandler  
   [ <attrlist> ] RaiseEvent(delegatesignature)  
      [ statements ]  
   End RaiseEvent  
End Event  
```  
  
## Части  
  
|||  
|-|-|  
|Отделение|Описание|  
|`attrlist`|Необязательно.  Список атрибутов, применимых к этому событию.  Несколько атрибутов разделяются запятыми.  [Список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) необходимо заключить в угловые скобки \(`<` и `>`\).|  
|`accessmodifier`|Необязательно.  Указывает, какой код может получать доступ к событию.  Ниже указаны доступные значения.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md) — любой код, который может получить доступ к объявляющему его элементу, может получить доступ к событию.<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md) — только код внутри его класса или производного класса может получить доступ к событию.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md) — только код в той же сборке может получить доступ к событию.<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md) — только код в объявляющем его элементе может получить доступ к событию.<br /><br /> Можно указать `Protected Friend` для предоставления доступа из кода в классе события, производном классе или той же сборке.|  
|`Shared`|Необязательно.  Указывает, что это событие не связано с определенным экземпляром класса или структуры.|  
|`Shadows`|Необязательно.  Указывает, что это событие повторно объявляет и скрывает программные элементы с одинаковыми именами или набор перегруженных элементов в базовом классе.  Можно скрыть любой тип объявленного элемента, используя любой другой тип.<br /><br /> Скрытый элемент недоступен из производного класса, который его скрывает, за исключением тех классов, из которых недоступен скрывающий элемент.  Например, если элемент `Private` скрывает элемент базового класса, то код, у которого нет разрешений на доступ к элементу `Private`, получает доступ к элементу базового класса.|  
|`eventname`|Обязательный.  Имя события; соответствует стандартным правилам именования переменных.|  
|`parameterlist`|Необязательно.  Список локальных переменных, которые представляют параметры этого события.  [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md) необходимо заключить в круглые скобки.|  
|`Implements`|Необязательно.  Указывает, что это событие реализует событие интерфейса.|  
|`implementslist`|Является обязательным, если предоставлен параметр `Implements`.  Список реализуемых процедур `Sub`.  Несколько процедур разделяются запятыми.<br /><br /> *implementedprocedure* \[ , *implementedprocedure* ...  \]<br /><br /> Каждый элемент `implementedprocedure` имеет перечисленные ниже синтаксис и компоненты.<br /><br /> `interface`.`definedname`<br /><br /> -   `interface` — обязательный.  Имя интерфейса, реализуемого классом или структурой, содержащими эту процедуру.<br />-   `Definedname` — обязательный.  Имя, под которым процедура определена в `interface`.  Оно не должно совпадать с `name`, именем, которое эта процедура использует для реализации определенной процедуры.|  
|`Custom`|Обязательный.  События, объявленные как `Custom`, должны определять настраиваемые методы доступа `AddHandler`, `RemoveHandler` и `RaiseEvent`.|  
|`delegatename`|Необязательно.  Имя делегата, указывающего подпись обработчика событий.|  
|`AddHandler`|Обязательный.  Объявляет метод доступа `AddHandler`, который задает операторы, выполняемые при добавлении обработчика событий, явно с помощью оператора `AddHandler` или неявно с помощью предложения `Handles`.|  
|`End AddHandler`|Обязательный.  Завершает блок `AddHandler`.|  
|`value`|Обязательный.  Имя параметра.|  
|`RemoveHandler`|Обязательный.  Объявляет метод доступа `RemoveHandler`, который задает операторы, выполняемые при удалении обработчика событий с помощью оператора `RemoveHandler`.|  
|`End RemoveHandler`|Обязательный.  Завершает блок `RemoveHandler`.|  
|`RaiseEvent`|Обязательный.  Объявляет метод доступа `RaiseEvent`, который задает операторы, выполняемые при создании события с помощью оператора `RaiseEvent`.  Как правило, при этом вызывается список делегатов, обслуживаемых методами доступа `AddHandler` и `RemoveHandler`.|  
|`End RaiseEvent`|Обязательный.  Завершает блок `RaiseEvent`.|  
|`delegatesignature`|Обязательный.  Список параметров, соответствующий параметрам, требуемым делегатом `delegatename`.  [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md) необходимо заключить в круглые скобки.|  
|`statements`|Необязательно.  Операторы, содержащие тела методов `AddHandler`, `RemoveHandler` и `RaiseEvent`.|  
|`End Event`|Обязательный.  Завершает блок `Event`.|  
  
## Заметки  
 После объявления события используйте оператор `RaiseEvent` для создания события.  Типичные события можно объявлять и создавать, как показано в следующих фрагментах кода.  
  
 [!CODE [VbVbalrEvents#13](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEvents#13)]  
  
> [!NOTE]
>  Аргументы событий можно объявлять так же, как аргументы процедур, за следующими исключениями: события не могут иметь именованные аргументы, аргументы `ParamArray` и аргументы `Optional`.  События не имеют возвращаемых значений.  
  
 Для обработки события его необходимо связать с подпрограммой обработчика событий с помощью оператора `Handles` или `AddHandler`.  Подписи подпрограммы и события должны совпадать.  Для обработки общего события необходимо использовать оператор `AddHandler`.  
  
 `Event` можно использовать только на уровне модуля.  Это означает, что *контекстом объявления* события должен быть класс, структура, модуль или интерфейс, но не исходный файл, пространство имен, процедура или блок.  Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 В большинстве случаев для объявления события можно использовать первый пример синтаксиса в разделе "Синтаксис" этой статьи.  Однако в некоторых сценариях требуется контролировать поведение события более детально.  Последний пример синтаксиса в разделе "Синтаксис" этой статьи, в котором используется ключевое слово `Custom`, обеспечивает такие возможности, позволяя определять настраиваемые события.  В настраиваемом событии можно точно указать, что происходит, когда код добавляет или удаляет обработчик события для события или когда код вызывает событие.  Примеры см. в разделе [Практическое руководство. Объявление пользовательских событий для экономии памяти](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md) и [Практическое руководство. Объявление пользовательских событий для предотвращения блокировки](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md).  
  
## Пример  
 В следующем примере события используются для выполнения обратного отсчета от 10 до 0 секунд.  Код иллюстрирует различные связанные с событиями методы, свойства и операторы.  В том числе оператор `RaiseEvent`.  
  
 Класс, который вызывает событие, является источником события, а методы, обрабатывающие события, — обработчиками событий.  Источник события может иметь несколько обработчиков для создаваемых им событий.  Когда класс создает событие, это событие создается во всех классах, выбранных для обработки событий данного экземпляра объекта.  
  
 В примере также используется форма \(`Form1`\) с кнопкой \(`Button1`\) и текстовым полем \(`TextBox1`\).  При нажатии кнопки в первом текстовом поле отображается обратный отсчет от 10 до 0 секунд.  По истечении всего времени \(10 секунд\) в первом текстовом поле отображается надпись Done.  
  
 Код для `Form1` указывает начальное и конечное состояния формы.  Он также содержит код, выполняемый при создании событий.  
  
 Чтобы использовать этот пример, откройте новый проект Windows Forms.  Затем добавьте кнопку с именем `Button1` и текстовое поле с именем `TextBox1` в главную форму с именем `Form1`.  Щелкните форму правой кнопкой мыши и выберите пункт **Просмотр кода**, чтобы открыть редактор кода.  
  
 Добавьте переменную `WithEvents` в раздел объявлений класса `Form1`:  
  
 [!CODE [VbVbalrEvents#14](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEvents#14)]  
  
 Добавьте следующий код в код для `Form1`.  Замените все повторяющиеся процедуры, которые могут существовать, такие как `Form_Load` или `Button_Click`.  
  
 [!CODE [VbVbalrEvents#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEvents#15)]  
  
 Нажмите клавишу F5 для запуска примера и нажмите кнопку **Start**.  Первое текстовое поле начинает обратный отсчет.  По истечении всего времени \(10 секунд\) в первом текстовом поле отображается надпись Done.  
  
> [!NOTE]
>  Способ обработки событий методом `My.Application.DoEvents` отличается от обработки событий формой.  Чтобы разрешить форме обрабатывать события напрямую, можно использовать многопоточность.  Дополнительные сведения см. в разделе [Потоки](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md).  
  
## См. также  
 [Оператор RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)   
 [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [События](../../../visual-basic/programming-guide/language-features/events/events.md)   
 [Оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [Оператор RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Практическое руководство. Объявление пользовательских событий для экономии памяти](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)   
 [Практическое руководство. Объявление пользовательских событий для предотвращения блокировки](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)   
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)