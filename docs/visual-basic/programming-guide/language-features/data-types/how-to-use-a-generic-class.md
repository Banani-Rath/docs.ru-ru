---
title: "Практическое руководство. Использование универсального класса (Visual Basic) | Microsoft Docs"
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
  - "параметры типа, определение"
  - "аргументы типа данных, определение"
  - "аргументы [Visual Basic], типы данных"
  - "ключевого слова, использование"
  - "универсальные параметры"
  - "параметры типа данных"
  - "универсальные шаблоны [Visual Basic], об универсальных шаблонах"
  - "типы данных [Visual Basic], в качестве параметров"
  - "типы данных [Visual Basic], в качестве аргументов"
  - "параметры, типы"
  - "типы [Visual Basic], универсальные"
  - "параметры, универсальные"
  - "универсальные шаблоны [Visual Basic], создание универсальных типов"
  - "аргументы типа данных"
  - "параметры, тип данных"
  - "параметры типа данных, определение"
  - "аргументы типа, определение"
  - "аргументы [Visual Basic], тип"
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Использование универсального класса (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Класс, принимающий *параметры типа*, называется *универсальным*. При использовании универсального класса из него можно создать *сконструированный класс*, указав *аргумент типа* для каждого из этих параметров. После этого можно объявить переменную типа сконструированного класса, а также создать экземпляр такого класса и присвоить его этой переменной.  
  
 Помимо классов, можно определять и использовать универсальные структуры, интерфейсы, процедуры и делегаты.  
  
 В следующей процедуре используется универсальный класс, определенный в [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], и создается его экземпляр.  
  
### Использование класса, который принимает параметр типа  
  
1.  Включите [Оператор Imports \(пространство имен .NET и тип\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) в начало файла исходного кода, чтобы импортировать пространство имен <xref:System.Collections.Generic?displayProperty=fullName>. Это позволяет ссылаться на класс <xref:System.Collections.Generic.Queue%601?displayProperty=fullName> без полного определения, чтобы его можно отличить от других классов очереди, таких как <xref:System.Collections.Queue?displayProperty=fullName>.  
  
2.  Создайте объект обычным способом, но добавьте `(Of` `type``)` сразу после имени класса.  
  
     Следующий пример использует тот же класс \(<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>\) для создания двух объектов очереди, содержащих элементы различных типов данных. Он добавляет элементы в конец каждой очереди и затем удаляет и отображает элементы из начала каждой очереди.  
  
     [!CODE [VbVbalrDataTypes#9](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrDataTypes#9)]  
  
## См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)   
 [Of](../../../../visual-basic/language-reference/statements/of-clause.md)   
 [Оператор Imports \(пространство имен .NET и тип\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Практическое руководство. Определение класса, реализующего одинаковую функциональность для различных типов данных](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)   
 [Итераторы](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)