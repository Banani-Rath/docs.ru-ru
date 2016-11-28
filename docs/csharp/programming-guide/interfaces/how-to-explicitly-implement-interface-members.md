---
title: "Практическое руководство. Явная реализация членов интерфейса (Руководство по программированию на C#) | Microsoft Docs"
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
  - "интерфейсы [C#], явная реализация"
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Явная реализация членов интерфейса (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В этом примере выполняется объявление [интерфейса](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, и класса, `Box`, который явно реализует члены интерфейса `getLength` и `getWidth`.  Доступ к этим членам осуществляется через экземпляр интерфейса `dimensions`.  
  
## Пример  
 [!CODE [csProgGuideInheritance#8](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#8)]  
  
## Отказоустойчивость  
  
-   Обратите внимание, что следующие строки в методе `Main` убраны в комментарий, так как иначе они вызвали бы ошибки компилятора.  Член интерфейса, реализованный явным образом, недоступен из экземпляра [класса](../../../csharp/language-reference/keywords/class.md).  
  
     [!CODE [csProgGuideInheritance#45](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#45)]  
  
-   Обратите также внимание, что следующие строки в методе `Main` успешно печатают размеры поля, поскольку эти методы вызываются из экземпляра интерфейса.  
  
     [!CODE [csProgGuideInheritance#46](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#46)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)   
 [Практическое руководство. Явная реализация членов двух интерфейсов](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)