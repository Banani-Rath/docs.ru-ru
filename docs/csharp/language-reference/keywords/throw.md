---
title: "throw (Справочник по C#) | Microsoft Docs"
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
  - "throw"
  - "throw_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "throw - ключевое слово [C#]"
  - "throw - оператор [C#]"
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# throw (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор `throw` используется для сообщения об аномальных ситуациях \(исключениях\) в ходе выполнения программы.  
  
## Заметки  
 Созданное исключение — это объект, класс которого унаследован от объекта <xref:System.Exception?displayProperty=fullName>, как показано в следующем примере.  
  
```  
class MyException : System.Exception {}  
// ...  
throw new MyException();  
```  
  
 Обычно оператор `throw` используется с операторами `try-catch` и `try-finally`.  Оператор [throw](../../../csharp/language-reference/keywords/throw.md) можно включить в блок `catch`, чтобы заново создать исключение, перехваченное блоком `catch`.  В этом случае оператор [throw](../../../csharp/language-reference/keywords/throw.md) не принимает операнд исключения.  Дополнительные сведения и примеры см. в разделах [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) и [Практическое руководство. Явное создание исключения](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md).  
  
## Пример  
 В этом примере демонстрируется вызов исключения с помощью оператора `throw`.  
  
 [!CODE [csrefKeywordsExceptions#5](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsExceptions#5)]  
  
## Пример кода  
 См. примеры в разделах [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) и [Практическое руководство. Явное создание исключения](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [Операторы try, catch и throw в C\+\+](../../../csharp/language-reference/keywords/try-catch.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Операторы обработки исключений](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [Практическое руководство. Явное создание исключения](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md)