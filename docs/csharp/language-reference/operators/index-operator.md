---
title: "Оператор (ссылка C#) | Microsoft Docs"
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
  - "[]_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "оператор индекса [C#]"
  - "квадратные скобки [ ] - оператор [C#]"
  - "[] - оператор [C#]"
  - "оператор индексирования [C#]"
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор (ссылка C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Квадратные скобки \(`[]`\) используются для массивов, индексаторов и атрибутов.  Кроме того, они могут использоваться с указателями.  
  
## Заметки  
 Тип массива указывается перед оператором `[]`:  
  
 [!CODE [csRefOperators#43](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#43)]  
  
 Для доступа к элементу массива его индекс необходимо заключить в скобки:  
  
 [!CODE [csRefOperators#44](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#44)]  
  
 Если индекс массива выходит за границы диапазона, происходит вызов исключения.  
  
 Перегрузка оператора индексирования массива невозможна; однако типы могут определять индексаторы и свойства, принимающие один или более параметров.  Параметры индексатора заключаются в квадратные скобки, как и индексы массива, но, в отличие от индексов массива, которые должны быть целочисленными, эти параметры могут быть любого типа.  
  
 Например, в платформе .NET Framework определен тип `Hashtable`, связывающий ключи и значения произвольного типа.  
  
 [!CODE [csRefOperators#45](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#45)]  
  
 Также квадратные скобки используются для определения [Атрибуты](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md):  
  
 [!CODE [csRefOperators#46](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#46)]  
  
 Квадратные скобки можно использовать для создания индекса из указателя.  
  
 [!CODE [csRefOperators#47](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#47)]  
  
 Проверка границ не выполняется.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Индексаторы](../../../csharp/programming-guide/indexers/index.md)   
 [небезопасное](../../../csharp/language-reference/keywords/unsafe.md)   
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)