---
title: "Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach (Руководство по программированию на C#) | Microsoft Docs"
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
  - "аргументы командной строки [C#]"
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Другим методом итерации всех элементов массива является использование оператора [foreach](../../../csharp/language-reference/keywords/foreach-in.md), как показано в следующем примере.  Оператор `foreach` можно использовать для итерации всех элементов массива, класса коллекции .NET Framework или любого класса или структуры, реализующих интерфейс <xref:System.Collections.IEnumerable>.  
  
> [!NOTE]
>  При выполнении приложения в Visual Studio можно указать аргументы командной строки в [Страница "Отладка" в конструкторе проектов](/visual-studio/ide/reference/debug-page-project-designer).  
  
## Пример  
 В данном примере показано, как напечатать аргументы командной строки с помощью оператора `foreach`.  
  
 [!CODE [csProgGuideMain#10](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideMain#10)]  
  
 [!CODE [csProgGuideMain#11](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideMain#11)]  
  
## См. также  
 <xref:System.Array>   
 <xref:System.Collections>   
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [Main\(\) и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Практическое руководство. Отображение аргументов командной строки](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Значения, возвращаемые методом Main\(\)](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)