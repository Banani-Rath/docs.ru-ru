---
title: "Предложение where (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "whereclause_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "where - предложение [C#]"
  - "where - ключевое слово [C#]"
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Предложение where (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Предложение `where` используется в выражении запроса для указания элементов, возвращаемых из источника данных, в выражении запроса.  Это предложение применяет логическое условие \(*предикат*\) к каждому исходному элементу \(со ссылкой переменной диапазона\) и возвращает элементы, для которых заданное условие является истинным.  В одном выражении запроса может присутствовать несколько предложений `where`, а в одном предложении – несколько частей выражения предиката.  
  
## Пример  
 В следующем примере предложение `where` фильтрует все числа за исключением тех, которые меньше пяти.  Если предложение `where` удалить, из источника данных будут возвращены все числа.  Выражение `num < 5` является предикатом, применяемым к каждому элементу.  
  
 [!CODE [cscsrefQueryKeywords#5](../CodeSnippet/VS_Snippets_VBCSharp/CsCsrefQueryKeywords#5)]  
  
## Пример  
 В одном предложении `where`  можно указать столько предикатов, сколько потребуется. Для этого необходимо использовать операторы [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) и [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md).  В следующем примере в запросе указано два предиката по порядку для выбора только четных чисел, которые меньше пяти.  
  
 [!CODE [cscsrefQueryKeywords#6](../CodeSnippet/VS_Snippets_VBCSharp/CsCsrefQueryKeywords#6)]  
  
## Пример  
 В предложении `where` может содержаться один или несколько методов, возвращающих логические значения.  В следующем примере предложение `where` использует метод, позволяющий определить, является ли текущее значение переменной диапазона четным или нет.  
  
 [!CODE [cscsrefQueryKeywords#7](../CodeSnippet/VS_Snippets_VBCSharp/CsCsrefQueryKeywords#7)]  
  
## Заметки  
 Предложение `where` представляет собой механизм фильтрации.  Это предложение можно поместить в любом месте выражения запроса, но только оно не может быть первым или последним.  Предложение `where` может размещаться до или после предложения [group](../../../csharp/language-reference/keywords/group-clause.md), в зависимости от того, когда требуется фильтрация исходных элементов – до или после группирования.  
  
 Если указанный предикат недопустим для элементов в источнике данных, возникнет ошибка времени выполнения.  Это одно преимущество строго\-типизированной проверки, обеспечиваемое [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)].  
  
 Во время выполнения ключевое слово `where` преобразуется в вызов метода стандартного оператора запроса <xref:System.Linq.Enumerable.Where%2A>.  
  
## См. также  
 [Ключевые слова запроса \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Предложение from](../../../csharp/language-reference/keywords/from-clause.md)   
 [Предложение select](../../../csharp/language-reference/keywords/select-clause.md)   
 [Filtering Data](../../../visual-basic/programming-guide/concepts/linq/filtering-data.md)   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)