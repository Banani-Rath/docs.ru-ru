---
title: "Универсальные методы (Руководство по программированию на C#) | Microsoft Docs"
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
  - "универсальные шаблоны [C#], методы"
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
caps.latest.revision: 27
caps.handback.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Универсальные методы (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Универсальный метод – это метод, объявляемый с параметрами типа, как в следующем примере.  
  
 [!CODE [csProgGuideGenerics#22](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#22)]  
  
 Следующий пример кода демонстрирует один способ вызова метода при помощи `int` для аргумента типа.  
  
 [!CODE [csProgGuideGenerics#23](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#23)]  
  
 Аргумент типа можно опустить и компилятор определит его.  Следующий вызов `Swap` эквивалентен предыдущему вызову.  
  
 [!CODE [csProgGuideGenerics#24](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#24)]  
  
 Те же правила определения типа применяются к статическим методам и методам экземпляров.  Компилятор может определить параметры типа на основе передаваемых аргументов метода; параметры типа не могут определяться им только исходя из ограничения или возвращаемого значения.  Таким образом, определение типа не работает для методов без параметров.  Определение типа происходит во время компиляции до того, как компилятор пытается разрешить подписи перегруженных методов.  Компилятор применяет логику определения типа ко всем универсальным методам с одним именем.  На шаге перегруженного разрешения компилятор включает только те универсальные методы, определение типа для которых было успешным.  
  
 В универсальном классе методы, не являющиеся универсальными, могут обращаться к параметрам типа уровня класса, как показано ниже.  
  
 [!CODE [csProgGuideGenerics#25](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#25)]  
  
 Если определить универсальный метод, принимающий те же параметры типа, что и содержащий класс, компилятор создаст предупреждение CS0693, так как внутри области метода аргумент, подставленный для внутреннего `T`, скрывает аргумент, подставленный для внешнего `T`.  Если требуется добиться гибкости вызова универсального метода класса с аргументами типа, отличными от предоставленных при создании экземпляра класса, следует подумать об использовании другого идентификатора для параметра типа метода, как показано в `GenericList2<T>` в следующем примере.  
  
 [!CODE [csProgGuideGenerics#26](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#26)]  
  
 Чтобы с параметрами типа в методах можно было выполнять более специализированные операции, используйте ограничения.  Текущую версию `Swap<T>`, которая теперь имеет имя `SwapIfGreater<T>`, можно использовать только с аргументами типа, реализующими <xref:System.IComparable%601>.  
  
 [!CODE [csProgGuideGenerics#27](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#27)]  
  
 Универсальные методы можно перегрузить в нескольких параметрах типа.  Например, все следующие методы можно разместить в одном и том же классе.  
  
 [!CODE [csProgGuideGenerics#28](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#28)]  
  
## Спецификация языка C\#  
 Дополнительные сведения см. в разделе [Спецификация языка C\#](../../../csharp/language-reference/language-specification.md).  
  
## См. также  
 <xref:System.Collections.Generic>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)