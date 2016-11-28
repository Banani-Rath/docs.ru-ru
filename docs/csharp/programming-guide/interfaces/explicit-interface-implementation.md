---
title: "Явная реализация интерфейса (Руководство по программированию в C#) | Microsoft Docs"
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
  - "явные интерфейсы [C#]"
  - "интерфейсы [C#], явные"
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Явная реализация интерфейса (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Если [класс](../../../csharp/language-reference/keywords/class.md) реализует два интерфейса, содержащих член с одинаковой сигнатурой, то при реализации этого члена в классе оба интерфейса будут использовать этот член для своей реализации.  В следующем примере все вызовы `Paint` вызывают один метод.  
  
 [!CODE [csProgGuideInheritance#39](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#39)]  
  
 Однако, если члены двух [интерфейсов](../../../csharp/language-reference/keywords/interface.md) не выполняют одинаковую функцию, это может привести к неверной реализации одного или обоих интерфейсов.  Возможна явная реализация члена интерфейса — путем создания члена класса, который вызывается только через интерфейс и имеет отношение только к этому интерфейсу.  Это достигается путем включения в имя члена класса имени интерфейса с точкой.  Например:  
  
 [!CODE [csProgGuideInheritance#40](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#40)]  
  
 Член класса `IControl.Paint` доступен только через интерфейс `IControl`, а член `ISurface.Paint` — только через интерфейс `ISurface`.  Каждая реализация метода является независимой и недоступна в классе напрямую.  Например:  
  
 [!CODE [csProgGuideInheritance#41](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#41)]  
  
 Явная реализация также используется для разрешения случаев, когда каждый из двух интерфейсов объявляет разные члены с одинаковым именем, например свойство и метод.  
  
 [!CODE [csProgGuideInheritance#42](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#42)]  
  
 Для реализации обоих интерфейсов классу необходимо использовать явную реализацию либо для свойства P, либо для метода P, либо для обоих членов, чтобы избежать ошибки компилятора.  Например:  
  
 [!CODE [csProgGuideInheritance#43](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#43)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)   
 [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md)