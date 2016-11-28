---
title: "Универсальные интерфейсы. (Руководство по программированию на C#) | Microsoft Docs"
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
  - "C# - язык, универсальные интерфейсы"
  - "универсальные шаблоны [C#], интерфейсы"
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
caps.latest.revision: 28
caps.handback.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Универсальные интерфейсы. (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Часто рекомендуется определять интерфейсы либо для универсальных классов коллекций, либо для универсальных классов, представляющих элементы в коллекции.  Приоритетным методом для универсальных классов является использование универсальных интерфейсов, таких как <xref:System.IComparable%601>, а не <xref:System.IComparable>, что позволяет избежать операций упаковки\-распаковки над типами значений.  Библиотека классов .NET Framework определяет несколько универсальных интерфейсов для использования с классами коллекций в пространстве имен <xref:System.Collections.Generic>.  
  
 Если интерфейс указан в качестве ограничения параметра типа, могут использоваться лишь типы, реализующие интерфейс.  В следующем примере кода показан класс `SortedList<T>`, который является производным от класса `GenericList<T>`.  Дополнительные сведения см. в разделе [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md).  `SortedList<T>` добавляет ограничение `where T : IComparable<T>`.  Это позволяет методу `BubbleSort` в `SortedList<T>` использовать универсальный метод <xref:System.IComparable%601.CompareTo%2A> в элементах списка.  В следующем примере элементы списка являются простым классом, `Person`, реализующим `IComparable<Person>`.  
  
 [!CODE [csProgGuideGenerics#29](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#29)]  
  
 В качестве ограничений для одного типа можно указать несколько интерфейсов. Это выполняется следующим образом.  
  
 [!CODE [csProgGuideGenerics#30](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#30)]  
  
 Интерфейс может определить несколько параметров типа, как показано далее.  
  
 [!CODE [csProgGuideGenerics#31](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#31)]  
  
 Правила наследования, которые применяются для классов, применимы и к интерфейсам.  
  
 [!CODE [csProgGuideGenerics#32](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#32)]  
  
 Универсальные интерфейсы могут наследовать от неуниверсальных, если первый тип интерфейсов является контравариантным, что означает использование его параметра типа в качестве возвращаемого значения.  В библиотеке классов .NET Framework <xref:System.Collections.Generic.IEnumerable%601> наследует от <xref:System.Collections.IEnumerable>, поскольку <xref:System.Collections.Generic.IEnumerable%601> использует только `T` в возвращаемом значении <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> и в методе считывания <xref:System.Collections.Generic.IEnumerator%601.Current%2A>.  
  
 Конкретные классы могут реализовать закрытые конструируемые интерфейсы следующим образом.  
  
 [!CODE [csProgGuideGenerics#33](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#33)]  
  
 Универсальные классы могут реализовать универсальные интерфейсы или закрытые конструируемые интерфейсы, если список параметров класса предоставляет все необходимые для интерфейса аргументы. Это выполняется следующим образом.  
  
 [!CODE [csProgGuideGenerics#34](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#34)]  
  
 Правила, управляющие перегрузкой методов, совпадают с правилами для методов в универсальных классах, структурах или интерфейсах.  Дополнительные сведения см. в разделе [Универсальные методы](../../../csharp/programming-guide/generics/generic-methods.md).  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [интерфейс](../../../csharp/language-reference/keywords/interface.md)   
 [Универсальные шаблоны](../Topic/Generics%20in%20the%20.NET%20Framework.md)