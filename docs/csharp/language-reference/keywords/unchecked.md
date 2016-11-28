---
title: "unchecked (справочник по C#) | Microsoft Docs"
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
  - "unchecked_CSharpKeyword"
  - "unchecked"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "unchecked - ключевое слово [C#]"
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# unchecked (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `unchecked` используется для подавления проверки переполнения при выполнении арифметических операций и преобразований с данными целого типа.  
  
 Если в непроверяемом контексте результатом выполнения выражения является значение, выходящее за допустимые пределы значений конечного типа, то переполнение не помечается.  Вычисление в приведенном ниже примере выполняется в блоке или выражении `unchecked`, поэтому факт превышения результатом максимального значения целого числа игнорируется и переменной `int1` присваивается значение \-2 147 483 639.  
  
 [!CODE [csrefKeywordsChecked#5](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsChecked#5)]  
  
 Если среда `unchecked` удалена, возникает ошибка компиляции.  Все члены данного выражения являются константами, поэтому переполнение можно обнаружить во время компиляции.  
  
 Выражения, содержащие неконстантные члены, не проверяются во время компиляции и выполнения по умолчанию.  Сведения о включении проверяемой среды см. в разделе [checked](../../../csharp/language-reference/keywords/checked.md).  
  
 Проверка на переполнение занимает некоторое время, поэтому использование непроверяемого кода в ситуациях, в которых отсутствует опасность переполнения, поможет повысить производительность.  Однако при наличии вероятности переполнения следует использовать проверяемую среду.  
  
## Пример  
 В этом примере показано, как использовать ключевое слово `unchecked`.  
  
 [!CODE [csrefKeywordsChecked#2](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsChecked#2)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Checked и Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)   
 [checked](../../../csharp/language-reference/keywords/checked.md)