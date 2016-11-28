---
title: "Практическое руководство. Создание событий базового класса в производных классах (Руководство по программированию в C#) | Microsoft Docs"
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
  - "события [C#], в производных классах"
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Создание событий базового класса в производных классах (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В следующем примере показан стандартный способ объявления событий в базовом классе таким образом, чтобы они могли создаваться и из производного класса.  Этот принцип широко используется в классах Windows Forms в библиотеке классов [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
 При создании класса, который может служить базовым для других классов, следует учитывать, что события являются делегатами особого типа, которые могут быть вызваны только из класса, который их объявил.  Производные классы не могут напрямую создавать события, объявленные в базовом классе.  Иногда нужно, чтобы событие могло создаваться только в базовом классе, однако чаще всего следует обеспечить производному классу возможность создания событий базового класса.  Для этого следует создать в базовом защищенный метод, предоставляющий оболочку для события.  Путем вызова или переопределения этого метода производные классы могут опосредованно вызывать событие.  
  
> [!NOTE]
>  Не следует объявлять виртуальные события в базовом классе и переопределять их в производном классе.  Компилятор c\#, не обрабатывает эти непрогнозируем правильно, и он будет ли подписка подписчика на событие фактически производного события базового класса.  
  
## Пример  
 [!CODE [csProgGuideEvents#1](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideEvents#1)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [События](../../../csharp/programming-guide/events/index.md)   
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)   
 [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Creating Event Handlers in Windows Forms](../Topic/Creating%20Event%20Handlers%20in%20Windows%20Forms.md)