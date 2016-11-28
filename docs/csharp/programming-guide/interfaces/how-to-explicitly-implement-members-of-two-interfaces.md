---
title: "Практическое руководство. Явная реализация членов двух интерфейсов (Руководство по программированию на C#) | Microsoft Docs"
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
  - "наследование [C#], явная реализация членов интерфейса"
  - "интерфейсы [C#], явная реализация с наследованием"
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Явная реализация членов двух интерфейсов (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Явная реализация [интерфейса](../../../csharp/language-reference/keywords/interface.md) позволяет программисту реализовать два интерфейса, имеющие одинаковые имена членов, и осуществить отдельную реализацию для каждого члена интерфейса.  В данном примере отображаются размеры окна как в метрических, так и в британских единицах измерения.  [Класс](../../../csharp/language-reference/keywords/class.md) "Box" реализует два интерфейса: IEnglishDimensions и IMetricDimensions, которые соответствуют различным системам измерения.  Оба интерфейса имеют одинаковые имена членов: "Length" и "Width".  
  
## Пример  
 [!CODE [csProgGuideInheritance#9](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#9)]  
  
## Отказоустойчивость  
 Если необходимо произвести измерения по умолчанию в британских единицах, реализуйте методы "Length" и "Width" в обычном режиме и явно реализуйте методы "Length" и "Width" из интерфейса IMetricDimensions:  
  
 [!CODE [csProgGuideInheritance#10](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#10)]  
  
 В этом случае можно получить доступ к британским единицам из экземпляра класса, а к метрическим единицам — из экземпляра интерфейса:  
  
 [!CODE [csProgGuideInheritance#11](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#11)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)   
 [Практическое руководство. Явная реализация членов интерфейса](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)