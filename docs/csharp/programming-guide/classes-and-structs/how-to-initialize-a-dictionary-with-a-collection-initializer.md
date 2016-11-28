---
title: "Практическое руководство. Инициализация словаря с помощью инициализатора коллекции (Руководство по программированию на C#). | Microsoft Docs"
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
  - "инициализаторы коллекций [C#], со словарем"
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Инициализация словаря с помощью инициализатора коллекции (Руководство по программированию на C#).
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

<xref:System.Collections.Generic.Dictionary%602> содержит коллекцию пар "ключ\-значение".  Метод <xref:System.Collections.Generic.Dictionary%602.Add%2A> берет два параметра, один для ключа и один для значения.  Для инициализации <xref:System.Collections.Generic.Dictionary%602> или любой коллекции, метод `Add` которой использует несколько параметров, следует заключить каждый набор параметров в скобки, как показано в следующем примере.  
  
## Пример  
 В следующем примере <xref:System.Collections.Generic.Dictionary%602> инициализируется экземплярами типа `StudentName`.  
  
 [!CODE [csProgGuideLINQ#34](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#34)]  
  
 Обратите внимание на две пары фигурных скобок в каждом элементе коллекции.  Внутренняя пара фигурных скобок заключает инициализатор объекта `StudentName`, а внешняя пара фигурных скобок — инициализатор пары "ключ\-значение", которая будет добавлена в коллекцию `students` <xref:System.Collections.Generic.Dictionary%602>.  И наконец, весь инициализатор коллекции для словаря заключается в фигурные скобки.  
  
## Компиляция кода  
 Для выполнения этого кода скопируйте класс в проект консольного приложения на языке Visual C\#, которое было создано в среде разработки [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)].  По умолчанию этот проект предназначен для версии 3.5 платформы [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] и имеет ссылку на библиотеку System.Core.dll и директиву для пространства имен System.Linq.  Если одно или более требований в проекте отсутствуют, их можно добавить вручную.  Дополнительные сведения см. в разделе [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Инициализаторы объектов и коллекций](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)