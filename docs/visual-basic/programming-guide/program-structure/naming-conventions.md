---
title: "Соглашения об именах Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "соглашения, кодирование в Visual Basic"
  - "имена, соглашения об именовании"
  - "имена, правила Visual Basic"
  - "соглашения об именовании"
  - "соглашения об именовании, классы"
  - "соглашения об именовании, Visual Basic"
  - "код Visual Basic, соглашения об именовании"
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Соглашения об именах Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

При присваивании имени элементу в приложении Visual Basic первым знаком имени должен быть алфавитный знак или подчеркивание.  Однако обратите внимание, что имена, начинающиеся с символа подчеркивания, не совместимы с [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\).  
  
 При присваивании имен необходимо учитывать следующие рекомендации.  
  
-   Каждое отдельное слово в имени следует начинать с большой буквы, например, `FindLastRecord` или `RedrawMyForm`.  
  
-   Первым словом в имени функции или метода следует ставить глагол, например `InitNameArray` or `CloseDialog`.  
  
-   Имя класса, структуры, модуля и свойства рекомендуется начинать с существительного, например `EmployeeName` или `CarAccessory`.  
  
-   Первым в имени интерфейса должен стоять префикс "I", вслед за которым идет имя существительное или именная группа, например `IComponent`, или имя прилагательное, описывающее поведение интерфейса, например `IPersistable`.  Рекомендуется не использовать знаки подчеркивания и аббревиатуры, поскольку аббревиатуры могут ввести в заблуждение.  
  
-   Имена обработчиков событий рекомендуется начинать с имени существительного, описывающего тип события, и дополнять его суффиксом "`EventHandler`", например "`MouseEventHandler`".  
  
-   К именам аргументов классов событий следует добавлять суффикс `EventArgs`.  
  
-   Если событие имеет смысл "до" или "после", следует использовать в его названии суффикс в настоящем или прошедшем времени, например "`ControlAdd`" или "`ControlAdded`".  
  
-   Для длинных или часто используемых терминов допустимо применять аббревиатуры разумной длины, например "HTML" вместо "Hypertext Markup Language".  В любом случае имена переменных длиной более 32 знаков плохо читаются на мониторе с небольшим разрешением.  Также следует проверить, последовательно ли используются аббревиатуры на протяжении всего приложения.  Попеременное использование в проекте "HTML" и "Hypertext Markup Language" может ввести в заблуждение.  
  
-   Следует избегать использования во внутренних областях имен, применяющихся также и во внешней области.  В случае доступа к неправильной переменной это вызовет ошибку.  Если произошел конфликт между переменной и ключевым словом с таким же именем, ключевое слово следует уточнить, добавив к его началу имя соответствующей библиотеки типов.  Например, при наличии переменной с именем `Date` можно использовать внутреннюю функцию `Date` только путем вызова <xref:System.DateTime.Date%2A?displayProperty=fullName>.  
  
## См. также  
 [Ключевые слова как имена элементов в коде](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)   
 [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md)