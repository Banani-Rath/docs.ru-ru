---
title: "Оператор &gt; (Справочник по C#) | Microsoft Docs"
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
  - ">_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "> - оператор [C#]"
  - "больше - оператор (>) [C#]"
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор &gt; (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Во всех числовых типах и типах перечислений определен оператор сравнения "больше" \(`>`\), который возвращает значение `true`, если первый операнд больше второго, в противном случае возвращается значение `false`.  
  
## Заметки  
 Типы, определенные пользователем, могут вызвать перегрузку оператора `>` \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  Если оператор `>` перегружен, то оператор [\<](../../../csharp/language-reference/operators/less-than-operator.md) тоже должен быть перегружен.  Если бинарный оператор перегружен, соответствующий оператор присваивания \(если таковой имеется\), также будет явно перегружен.  
  
## Пример  
 [!CODE [csRefOperators#29](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#29)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)   
 [явные](../../../csharp/language-reference/keywords/explicit.md)