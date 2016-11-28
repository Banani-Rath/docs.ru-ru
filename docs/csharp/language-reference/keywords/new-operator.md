---
title: "Оператор new (Справочник по C#) | Microsoft Docs"
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
  - "new operator - ключевое слово [C#]"
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор new (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Используется для создания объектов и вызова конструкторов.  Примеры.  
  
```  
Class1 obj  = new Class1();  
```  
  
 Он также используется для создания экземпляров анонимных типов.  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 С помощью оператора `new` можно вызвать заданный по умолчанию конструктор для типов значений.  Примеры.  
  
```  
int i = new int();  
```  
  
 В предыдущем операторе `i` инициализируется значением `0`, которое является значением по умолчанию для типа `int`.  Этот оператор приводит к результату, представленному далее.  
  
```  
int i = 0;  
```  
  
 Полный список значений по умолчанию см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).  
  
 Следует помнить, что объявление конструктора по умолчанию для [структуры](../../../csharp/language-reference/keywords/struct.md) является ошибкой, поскольку каждый тип значения неявно имеет открытый заданный по умолчанию конструктор.  Можно объявить параметризованные конструкторы в типе структуры, чтобы задать начальные значения, однако это необходимо, только если требуются значения, отличные от установленных по умолчанию.  
  
 Объекты типа значения, например структуры, создаются в стеке, тогда как объекты ссылочного типа, например классы, создаются в куче.  Уничтожение обоих типов объектов выполняется автоматически, но объекты на основе типов значений удаляются при выходе за рамки области действия, а объекты на основе ссылочных типов — в неуказанное время после удаления последней ссылки, указывающей на них.  Для ссылочных типов, использующих фиксированные ресурсы, например большой объем памяти, файловые дескрипторы, сетевые подключения, иногда рекомендуется использовать детерминированную финализацию для обеспечения скорейшего уничтожения объекта.  Дополнительные сведения см. в разделе [Оператор using](../../../csharp/language-reference/keywords/using-statement.md).  
  
 Оператор `new` перегрузить нельзя.  
  
 Если оператору `new` не удается выделить память, от создает исключение <xref:System.OutOfMemoryException>.  
  
## Пример  
 В следующем примере создается объект `struct` и класс объекта, которые инициализируются с помощью оператора `new`, после чего им присваиваются значения.  Отображаются заданные по умолчанию и присвоенные значения.  
  
 [!CODE [csrefKeywordsOperator#7](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsOperator#7)]  
  
 Обратите внимание, что в примере строка имеет значение по умолчанию `null`.  Поэтому она не отображается.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)