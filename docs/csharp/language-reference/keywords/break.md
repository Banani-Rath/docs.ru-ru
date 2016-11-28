---
title: "break (Справочник по C#) | Microsoft Docs"
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
  - "break"
  - "break_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "break - ключевое слово [C#]"
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# break (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор `break` завершает ближайший внешний цикл или оператор [switch](../../../csharp/language-reference/keywords/switch.md), в котором он появляется.  Управление передается оператору, следующему за завершенным оператором \(если таковой имеется\).  
  
## Пример  
 В этом примере условный оператор содержит счетчик, который должен считать от 1 до 100; однако оператор `break` завершает цикл после четырех.  
  
 [!CODE [csrefKeywordsJump#1](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsJump#1)]  
  
## Пример  
 В этом примере для разрыва внутреннего вложенного цикла и возвращения управления во внешний цикл используется оператор `break`.  
  
 [!CODE [csrefKeywordsJump#7](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsJump#7)]  
  
## Пример  
 В этом примере показано использование `break` в операторе [switch](../../../csharp/language-reference/keywords/switch.md).  
  
 [!CODE [csrefKeywordsJump#2](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsJump#2)]  
  
 При вводе `4` будет следующий результат.  
  
```  
Enter your selection (1, 2, or 3): 4  
Sorry, invalid selection.  
```  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [switch](../../../csharp/language-reference/keywords/switch.md)   
 [Операторы перехода](../../../csharp/language-reference/keywords/jump-statements.md)   
 [Операторы итерации](../../../csharp/language-reference/keywords/iteration-statements.md)