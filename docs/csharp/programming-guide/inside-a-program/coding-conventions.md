---
title: "Соглашения о написании кода на C# (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# - язык, соглашения о написании кода"
  - "соглашения о написании кода, C#"
  - "Visual C#, соглашения о написании кода"
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: 32
caps.handback.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Соглашения о написании кода на C# (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[Спецификация языка C\#](http://go.microsoft.com/fwlink/?LinkId=199552) не определяет стандарт кодирования.  Однако корпорация Майкрософт использует приведенные в этом разделе рекомендации для разработки примеров и документации.  
  
 Соглашения о написании кода предназначены для реализации следующих целей.  
  
-   Создание согласованного вида кода, позволяющего читателям сосредоточиться на содержимом, а не на структуре.  
  
-   Предоставление читателям возможности делать предположения, основанные на опыте, и поэтому быстрее понимать код.  
  
-   Упрощение процессов копирования, изменения и обслуживания кода.  
  
-   Предоставление лучших методик C\#.  
  
## Соглашения об именах  
  
-   В короткие примерах, не содержащих [директив using](../../../csharp/language-reference/keywords/using-directive.md), рекомендуется использовать полные указания для пространства имен.  Если известно, что пространство имен импортировано в проект по умолчанию, не требуется указывать полные имена из этого пространства имен.  Полные имена, если они слишком длинные для одной строки, можно разбить после точки \(.\), как показано в следующем примере.  
  
     [!CODE [csProgGuideCodingConventions#1](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#1)]  
  
-   Нет необходимости изменять имена объектов, созданных с помощью инструментов разработки Visual Studio, чтобы привести их в соответствие с другими соглашениями.  
  
## Соглашения о расположении  
 Чтобы выделить структуру кода и облегчить чтение кода, в хорошем макете используется форматирование.  Примеры и образцы корпорации Майкрософт соответствуют следующим соглашениям.  
  
-   Использование параметров редактора кода по умолчанию \(логичные отступы, отступы по четыре символа, использование пробелов для табуляции\).  Дополнительные сведения см. в разделе ["Параметры", "Текстовый редактор", C\#, "Форматирование"](/visual-studio/ide/reference/options-text-editor-csharp-formatting)  
  
-   Запись только одного оператора в строке.  
  
-   Запись только одного объявления в строке.  
  
-   Если отступ для дополнительных строк не ставится автоматически, необходимо сделать для них отступ на одну позицию табуляции \(четыре пробела\).  
  
-   Добавление по крайней мере одной пустой строки между определениями методов и свойств.  
  
-   Использование скобок для ясности предложений в выражениях, как показано в следующем коде.  
  
     [!CODE [csProgGuideCodingConventions#2](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#2)]  
  
## Соглашения о комментариях  
  
-   Комментарий размещается на отдельной строке, а не в конце строки кода.  
  
-   Текст комментария начинается с заглавной буквы.  
  
-   Текст комментария завершается точкой.  
  
-   Между разделителем комментария \(\/ \/\) и текстом комментария вставляется один пробел, как показано в следующем примере.  
  
     [!CODE [csProgGuideCodingConventions#3](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#3)]  
  
-   Вокруг комментариев не должно быть звездочек.  
  
## Рекомендации по работе с языком  
 В следующих подразделах описаны методики, которыми руководствуется команда C\# для подготовки примеров и образцов кода.  
  
### Тип данных String  
  
-   Для сцепления коротких строк рекомендуется использовать оператор `+`, как показано в следующем коде.  
  
     [!CODE [csProgGuideCodingConventions#6](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#6)]  
  
-   Для добавления строк в циклы, особенно при работе с текстами больших размеров, рекомендуется использовать объект <xref:System.Text.StringBuilder>.  
  
     [!CODE [csProgGuideCodingConventions#7](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#7)]  
  
### Неявно типизированные локальные переменные  
  
-   В случаях, когда тип переменной понятен из правой части назначения или когда точный тип не важен, рекомендуется использовать [неявное типизирование](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) для локальных переменных.  
  
     [!CODE [csProgGuideCodingConventions#8](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#8)]  
  
-   Если тип из правой части назначения не является очевидным, не рекомендуется использовать [var](../../../csharp/language-reference/keywords/var.md).  
  
     [!CODE [csProgGuideCodingConventions#9](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#9)]  
  
-   При указании типа переменной не следует полагаться на имя переменной.  Имя может быть неверным.  
  
     [!CODE [csProgGuideCodingConventions#10](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#10)]  
  
-   Рекомендуется избегать использования `var` вместо [dynamic](../../../csharp/language-reference/keywords/dynamic.md).  
  
-   Рекомендуется использовать неявное типизирование для определения типа переменной цикла в циклах [for](../../../csharp/language-reference/keywords/for.md) и [foreach](../../../csharp/language-reference/keywords/foreach-in.md).  
  
     В следующем примере неявное типизирование используется в операторе `for`.  
  
     [!CODE [csProgGuideCodingConventions#11](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#11)]  
  
     В следующем примере неявное типизирование используется в операторе `foreach`.  
  
     [!CODE [csProgGuideCodingConventions#12](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#12)]  
  
### Беззнаковый тип данных  
  
-   Как правило, рекомендуется использовать `int` вместо беззнаковых типов.  В C\# обычно используется `int`. Использование `int` упрощает взаимодействие с другими библиотеками.  
  
### Массивы  
  
-   При инициализации массивов в строке объявления рекомендуется использовать сокращенный синтаксис.  
  
     [!CODE [csProgGuideCodingConventions#13](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#13)]  
  
### Делегаты  
  
-   Для создания экземпляров типа делегата рекомендуется использовать сокращенный синтаксис.  
  
     [!CODE [csProgGuideCodingConventions#14](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#14)]  
  
     [!CODE [csProgGuideCodingConventions#15](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#15)]  
  
### Операторы try\-catch и using в процессе обработки исключений  
  
-   Рекомендуется использовать оператор [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) для обработки большей части исключений.  
  
     [!CODE [csProgGuideCodingConventions#16](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#16)]  
  
-   Использование [оператора C\# using](../../../csharp/language-reference/keywords/using-statement.md) упрощает код.  При наличии оператора [try\-finally](../../../csharp/language-reference/keywords/try-finally.md), в котором единственное, что делает код в блоке `finally`, это вызов метода <xref:System.IDisposable.Dispose%2A>, рекомендуется вместо него использовать оператор `using`.  
  
     [!CODE [csProgGuideCodingConventions#17](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#17)]  
  
### Операторы & & и &#124;&#124;  
  
-   Чтобы избежать возникновения исключений и увеличить производительность за счет пропуска необязательных сравнения, рекомендуется использовать [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) вместо [&](../../../csharp/language-reference/operators/and-operator.md) и [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) вместо                                       [&#124;](../../../csharp/language-reference/operators/or-operator.md) при выполнении сравнений, как показано в следующем примере.  
  
     [!CODE [csProgGuideCodingConventions#18](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#18)]  
  
### Оператор New  
  
-   Рекомендуется использовать сокращенную форму создания экземпляра для объекта с неявным типизированием, как показано в следующем объявлении.  
  
     [!CODE [csProgGuideCodingConventions#19](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#19)]  
  
     Предыдущая строка соответствует следующему объявлению.  
  
     [!CODE [csProgGuideCodingConventions#20](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#20)]  
  
-   Рекомендуется использовать инициализаторы объектов для упрощения создания объектов.  
  
     [!CODE [csProgGuideCodingConventions#21](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#21)]  
  
### Обработка событий  
  
-   При определении обработчика событий, которого не требуется удалять позднее, рекомендуется использовать лямбда\-выражение.  
  
     [!CODE [csProgGuideCodingConventions#22](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#22)]  
  
     [!CODE [csProgGuideCodingConventions#23](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#23)]  
  
### Статический члены  
  
-   Для вызова [статических](../../../csharp/language-reference/keywords/static.md) членов следует использовать имя класса: *ClassName.StaticMember*.  В этом случае код становится более удобочитаемым за счет четкого доступа.  Не присваивайте статическому члену, определенному в базовом классе, имя производного класса.  Во время компиляции кода его читаемость нарушается, и если добавить статический член с тем же именем в производный классе, код может быть поврежден.  
  
### Запросы LINQ  
  
-   Используйте значимые имена для переменных запроса.  В следующем примере используется `seattleCustomers` для клиентов, находящихся в Сиэтле.  
  
     [!CODE [csProgGuideCodingConventions#25](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#25)]  
  
-   Рекомендуется использовать псевдонимы для уверенности в том, что в именах свойств анонимных типов верно используются прописные буквы при помощи правил использования прописных и строчных букв языка Pascal.  
  
     [!CODE [csProgGuideCodingConventions#26](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#26)]  
  
-   Переименуйте свойства, если имена свойств в результате могут быть неоднозначными.  Например, если запрос возвращает имя клиента и идентификатор распространителя, не оставляйте имена в виде `Name` и `ID`, а переименуйте их, чтобы было ясно, что `Name` — имя клиента и `ID` — идентификатор распространителя.  
  
     [!CODE [csProgGuideCodingConventions#27](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#27)]  
  
-   Рекомендуется использовать неявное типизирование в объявлении переменных запроса и переменных диапазона.  
  
     [!CODE [csProgGuideCodingConventions#25](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#25)]  
  
-   Выравнивайте предложения запроса под предложением [from](../../../csharp/language-reference/keywords/from-clause.md), как показано в предыдущих примерах.  
  
-   Чтобы гарантировать, что более поздние предложения запроса работают с ограниченным, отфильтрованным набором данных, используйте предложение [where](../../../csharp/language-reference/keywords/where-clause.md) перед другими предложениями запроса.  
  
     [!CODE [csProgGuideCodingConventions#29](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#29)]  
  
-   Используйте несколько предложений `from` для доступа к внутренним коллекциям вместо предложения [join](../../../csharp/language-reference/keywords/join-clause.md).  Например, коллекция объектов `Student` может содержать коллекцию результатов тестирования.  При выполнении следующего запроса возвращаются результаты, превышающие 90 балов, а также фамилии учащихся, получивших такие оценки.  
  
     [!CODE [csProgGuideCodingConventions#30](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#30)]  
  
## Безопасность  
 Следуйте указаниям, изложенным в [Secure Coding Guidelines](../Topic/Secure%20Coding%20Guidelines.md).  
  
## См. также  
 [Соглашения о написании кода в Visual Basic](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)   
 [Secure Coding Guidelines](../Topic/Secure%20Coding%20Guidelines.md)