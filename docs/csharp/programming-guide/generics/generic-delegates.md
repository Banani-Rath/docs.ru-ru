---
title: "Универсальные делегаты. (Руководство по программированию на C#) | Microsoft Docs"
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
  - "делегаты [C#], универсальный"
  - "универсальные шаблоны [C#], делегаты"
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Универсальные делегаты. (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[Делегат](../../../csharp/language-reference/keywords/delegate.md) может определять собственные параметры\-типы.  Код, ссылающийся на универсальный делегат, может указать аргумент типа для создания закрытого конструируемого типа так же, как и при создании универсального класса или вызове универсального метода, как показано в следующем примере.  
  
 [!CODE [csProgGuideGenerics#36](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#36)]  
  
 В C\# версии 2.0 представлена новая функция, которая называется преобразованием группы методов. Она применяется как к конкретным, так и к универсальным типам делегатов и позволяет записывать предыдущую строку с помощью следующего упрощенного синтаксиса.  
  
 [!CODE [csProgGuideGenerics#37](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#37)]  
  
 Делегаты, определенные в универсальном классе, могут использовать параметры типа универсального класса так же, как и методы класса.  
  
 [!CODE [csProgGuideGenerics#38](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#38)]  
  
 Код, ссылающийся на делегат, должен указать аргумент типа содержащего класса следующим образом.  
  
 [!CODE [csProgGuideGenerics#39](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#39)]  
  
 Универсальные делегаты особенно полезны при определении событий на основе типичного шаблона разработки, поскольку аргумент отправителя может быть строго типизированным и его больше нельзя привести к типу <xref:System.Object> и из него  
  
 [!CODE [csProgGuideGenerics#40](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#40)]  
  
## См. также  
 <xref:System.Collections.Generic>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Универсальные методы](../../../csharp/programming-guide/generics/generic-methods.md)   
 [Универсальные классы](../../../csharp/programming-guide/generics/generic-classes.md)   
 [Универсальные интерфейсы](../../../csharp/programming-guide/generics/generic-interfaces.md)   
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)   
 [Универсальные шаблоны](../Topic/Generics%20in%20the%20.NET%20Framework.md)