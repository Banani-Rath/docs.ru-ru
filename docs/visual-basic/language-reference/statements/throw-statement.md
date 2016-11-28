---
title: "Оператор Throw (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Throw"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "обработка исключений, throw - оператор"
  - "обработка исключений, неструктурированный"
  - "On Error - оператор, создание исключений"
  - "структурированная обработка исключений, throw - операторы"
  - "throw - оператор"
  - "throw - оператор, сведения об операторах throw"
  - "создание исключений"
  - "создание исключений, throw - оператор"
  - "обработка исключений try-catch, throw - операторы"
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор Throw (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Вызывает исключение внутри процедуры.  
  
## Синтаксис  
  
```  
Throw [ expression ]  
```  
  
## Часть  
 `expression`  
 Предоставляет сведения о создаваемом исключении.  Является необязательным, когда находится в операторе `Catch`, в противном случае является обязательным.  
  
## Заметки  
 Оператор `Throw` создает исключение, которое можно обрабатывать с помощью кода структурированной обработки исключений \(`Try`...`Catch`...`Finally`\) или кодом неструктурированной обработки исключений \(`On Error GoTo`\).  Оператор `Throw` можно использовать для перехвата ошибок внутри кода, поскольку в Visual Basic стек вызовов перемещается наверх до тех пор, пока не будет найден соответствующий код обработки исключений.  
  
 Оператор `Throw` без выражения может использоваться только в операторе `Catch`; в этом случае оператор возвращает исключение, обрабатываемое в данный момент оператором `Catch`.  
  
 Оператор `Throw` сбрасывает стек вызовов для исключения `expression`.  Если исключение `expression` не указано, стек вызовов остается неизменным.  Можно получить доступ к стеку вызовов для исключения с помощью свойства <xref:System.Exception.StackTrace%2A>.  
  
## Пример  
 В следующем коде для создания исключения используется оператор `Throw`:  
  
 [!CODE [VbVbalrStatements#84](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#84)]  
  
## Требования  
 **Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Модуль:** `Interaction`  
  
 **Сборка:** библиотека времени выполнения Visual Basic \(в Microsoft.VisualBasic.dll\)  
  
## См. также  
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)