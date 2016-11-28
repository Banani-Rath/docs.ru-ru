---
title: "Арифметические операции над указателями (Руководство по программированию в C#) | Microsoft Docs"
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
  - "указатели [C#], арифметические операции"
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Арифметические операции над указателями (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В этом разделе рассматривается использование арифметических операторов `+` и **\-** для управления указателями.  
  
> [!NOTE]
>  Невозможно выполнять арифметические операции над указателями типа "void".  
  
## Сложение и вычитание числовых значений из указателей  
 Можно добавить значение `n` типа [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md) к указателю `p` `` любого типа, кроме `void*`.  В результате `p+n` получится указатель, являющийся суммой `n * sizeof(p) to the address of p`.  Аналогично, результатом `p-n` является указатель, полученный вычитанием `n * sizeof(p)` из адреса `p`.  
  
## Вычитание указателей  
 Также можно вычитать указатели одного типа.  Тип результата всегда `long`.  Например, если `p1` и `p2` являются указателями типа `pointer-type*`, то результат выражения `p1-p2` будет следующим:  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 При переполнении домена указателя в результате выполнения арифметической операции исключений не генерируется, а результат зависит от конкретной реализации.  
  
## Пример  
 [!CODE [csProgGuidePointers#14](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#14)]  
  
 [!CODE [csProgGuidePointers#15](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#15)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)   
 [Обработка указателей](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)   
 [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Типы](../../../csharp/language-reference/keywords/types.md)   
 [небезопасное](../../../csharp/language-reference/keywords/unsafe.md)   
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)