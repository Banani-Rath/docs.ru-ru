---
title: "C# Features That Support LINQ | Microsoft Docs"
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
  - "LINQ [C#], features supporting LINQ"
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
caps.latest.revision: 23
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# C# Features That Support LINQ
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В этом разделе представлены новые конструкции языка C\# 3.0.  Хотя все эти новые возможности в той или иной степени используются с запросами [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], они не привязаны к [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] и могут использоваться в любом контексте, где будут целесообразны.  
  
## Выражения запросов  
 Выражения запросов используют декларативный синтаксис, аналогичный SQL или XQuery для запросов к коллекциям через интерфейс IEnumerable.  При компиляции синтаксис запроса преобразуется в вызовы методов расширения стандартных операторов запросов, реализованные поставщиком [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].  Приложения управляют стандартными операторами запросов, которые находятся в области действия, за счет указания соответствующего пространства имен с помощью директивы `using`.  Следующее выражение запроса принимает массив строк, группирует их в соответствии с первым знаком в строке и упорядочивает группы.  
  
```  
var query = from str in stringArray  
            group str by str[0] into stringGroup  
            orderby stringGroup.Key  
            select stringGroup;  
```  
  
 Дополнительные сведения см. в разделе [Выражения запросов LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md).  
  
## Неявно типизированные переменные \(var\)  
 Вместо явного задания типа при объявлении и инициализации переменной можно использовать модификатор [var](../../../../csharp/language-reference/keywords/var.md),чтобы сообщить компилятору о необходимости определить и присвоить тип, как показано ниже.  
  
```  
var number = 5;  
var name = "Virginia";  
var query = from str in stringArray  
            where str[0] == 'm'  
            select str;  
```  
  
 Переменные, объявленные как `var`, так же строго типизированы, как и переменные с явно указанным типом.  Использование `var` дает возможность создавать анонимные типы, но она может применяться и для любых локальных переменных.  Массивы также могут быть объявлены с неявным типом.  
  
 Дополнительные сведения см. в разделе [Неявно типизированные локальные переменные](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## Инициализаторы объектов и коллекций  
 Инициализаторы объектов и коллекций позволяют инициализировать объекты без явного вызова конструктора для объектов.  Инициализаторы обычно используются в выражениях запроса при проецировании исходных данных на новый тип данных.  Предположим, что класс с именем `Customer` имеет открытые свойства `Name` и `Phone` и инициализатор объекта может использоваться как в следующем коде.  
  
```  
Customer cust = new Customer { Name = "Mike", Phone = "555-1212" };  
```  
  
 Дополнительные сведения см. в разделе [Инициализаторы объектов и коллекций](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## Анонимные типы  
 Анонимный тип создается компилятором и его имя доступно только компилятору.  Анонимные типы предоставляют удобный способ временной группировки набора свойств в результатах запроса без необходимости определения отдельного именованного типа.  Анонимные типы инициализируются выражением new и инициализатором объектов, как показано ниже.  
  
```  
select new {name = cust.Name, phone = cust.Phone};  
```  
  
 Дополнительные сведения см. в разделе [Анонимные типы](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
## К методам расширения  
 Метод расширения представляет собой статический метод, который может быть связан с типом так, что он может быть вызван, как если бы он был методом экземпляра этого типа.  Эта возможность позволяет, по сути, "добавить" новые методы в существующие типы, фактически не изменяя их.  Стандартные операторы запросов представляют собой набор методов расширения, предоставляющих функциональные возможности запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] для любого типа, который реализует <xref:System.Collections.Generic.IEnumerable%601>.  
  
 Дополнительные сведения см. в разделе [Методы расширения](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
## Лямбда\-выражения  
 Лямбда\-выражение является встроенной функцией, использующей оператор \=\> для отделения входных параметров от основной части функции, и может быть преобразована во время компиляции в делегат или дерево выражения.  В программировании [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] лямбда\-выражения встречаются при использовании прямых вызовов стандартных операторов запросов.  
  
 Дополнительные сведения см. в следующих разделах.  
  
-   [Анонимные функции](../../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [Лямбда\-выражения](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [Деревья выражений](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)  
  
## Автоматически реализуемые свойства  
 Автоматически реализуемые свойства делают объявление свойств более кратким.  При объявлении свойств, как показано в следующем примере, компилятор создаст закрытое, анонимное резервное поле, которое доступно исключительно с помощью методов get и set свойства.  
  
```  
public string Name {get; set;}  
```  
  
 Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
## См. также  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Visual Basic Features That Support LINQ](../../../../visual-basic/programming-guide/concepts/linq/features-that-support-linq.md)