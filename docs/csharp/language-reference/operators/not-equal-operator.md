---
title: "Оператор != (справочник по C#) | Microsoft Docs"
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
  - "!=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "!= - оператор [C#]"
  - "оператор неравенства (!=) [C#]"
  - "оператор неравенства (!=) [C#]"
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор != (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор неравенства \(`!=`\) возвращает значение false, если его операнды равны, в противном случае — значение true.  Операторы неравенства предопределены для всех типов, включая строку и объект.  Типы, определенные пользователем, могут вызвать перегрузку оператора `!=`.  
  
## Заметки  
 Для предопределенных типов значений оператор неравенства \(`!=`\) возвращает значение true, если значения его операндов совпадают, в противном случае — значение false.  Для ссылочных типов, отличных от `string`, оператор `!=` возвращает значение true, если оба его операнда ссылаются на разные объекты.  Для типа `string` оператор `!=` сравнивает значения строк.  
  
 Типы значений, определенные пользователем, могут вызвать перегрузку оператора `!=` \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  Ее могут вызвать и пользовательские ссылочные типы, хотя по умолчанию оператор `!=` работает в соответствии с приведенным выше описанием как для предопределенных, так и пользовательских ссылочных типов.  Если оператор `!=` перегружен, то оператор [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md) тоже должен быть перегружен.  Операции над целыми типами обычно разрешены в перечислениях.  
  
## Пример  
 [!CODE [csRefOperators#33](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#33)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)