---
title: "Параметры универсального типа (Руководство по программированию на C#) | Microsoft Docs"
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
  - "универсальные шаблоны [C#], параметры типа"
  - "параметры типа [C#]"
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Параметры универсального типа (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В определении универсального типа или метода параметры типа представляют собой заполнитель для определенного типа, задаваемого клиентом при создании переменной универсального типа.  Универсальный класс, такой как `GenericList<T>` listed in [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md), нельзя использовать "как есть", поскольку он является не типом а, скорее, чертежом типа.  Для работы с `GenericList<T>` в клиентском коде необходимо объявить и создать конструируемый тип, указав в угловых скобках аргумент типа.  Аргумент\-тип для этого конкретного класса может быть любым типом, распознаваемым компилятором.  Можно создать любое количество экземпляров конструируемых типов, и каждый из них может использовать разные аргументы типа, как показано далее.  
  
 [!CODE [csProgGuideGenerics#7](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#7)]  
  
 В каждом экземпляре `GenericList<T>` каждое вхождение `T` в классе будет заменено во время выполнения аргументом типа.  С помощью данной замены было создано три отдельных типобезопасных и эффективных объекта, использующих определение класса.  Дополнительные сведения о выполнении этой замены в CLR см. раздел [Универсальные типы во время выполнения](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
## Рекомендации по именованию параметра типа  
  
-   При именовании параметров универсальных типов **используйте** описательные имена, если только однобуквенное имя не является полностью понятным без пояснений, вследствие чего нет необходимости применять описательное имя.  
  
     [!CODE [csProgGuideGenerics#8](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#8)]  
  
-   Для типов с однобуквенными параметрами **рекомендуется** использовать "T" в качестве имени параметра типа.  
  
     [!CODE [csProgGuideGenerics#9](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#9)]  
  
-   К описательным именам параметров типа **добавляйте** префикс "T".  
  
     [!CODE [csProgGuideGenerics#10](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#10)]  
  
-   В имени параметра **рекомендуется** указывать ограничения, накладываемые на параметр типа.  Например, параметр, предназначенный только для `ISession`, может называться `TSession`.  
  
## См. также  
 <xref:System.Collections.Generic>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)   
 [Различия между шаблонами языка C\+\+ и универсальными шаблонами языка C\#](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)