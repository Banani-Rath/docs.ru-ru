---
title: "Передача массивов в качестве аргументов (Руководство по программированию на C#) | Microsoft Docs"
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
  - "массивы [C#], передача в качестве аргументов"
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Передача массивов в качестве аргументов (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Массивы можно передавать в качестве аргументов для параметров методов.  Поскольку массивы являются ссылочными типами, метод может изменять значение элементов.  
  
## Передача одномерных массивов в качестве аргументов  
 Инициализированный одномерный массив можно передать в метод.  Например, следующая инструкция передает массив в метод печати.  
  
 [!CODE [csProgGuideArrays#34](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#34)]  
  
 В следующем примере кода показана частичная реализация метода печати.  
  
 [!CODE [csProgGuideArrays#33](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#33)]  
  
 Инициализацию и передачу нового массива можно выполнить в рамках одного шага, как показано в следующем примере.  
  
 [!CODE [CsProgGuideArrays#35](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#35)]  
  
## Пример  
  
### Описание  
 В следующем примере массив строк инициализируется и передается в качестве аргумента метода `PrintArray`.  Затем метод отображает элементы этого массива.  Затем вызываются методы `ChangeArray` и `ChangeArrayElement` для демонстрации того, что отправка аргумента массива по значению не запрещает вносить изменения в элементы массива.  
  
### Код  
 [!CODE [csProgGuideArrays#30](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#30)]  
  
## Передача многомерных массивов в качестве аргументов  
 Инициализированный многомерный массив передается методу так же, как и одномерный массив.  
  
 [!CODE [csProgGuideArrays#41](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#41)]  
  
 В следующем примере кода показано частичное объявление метода печати, который принимает в качестве аргумента двумерный массив.  
  
 [!CODE [csProgGuideArrays#36](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#36)]  
  
 Инициализацию и передачу нового массива можно выполнить в рамках одного шага, как показано в следующем примере.  
  
 [!CODE [csProgGuideArrays#32](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#32)]  
  
## Пример  
  
### Описание  
 В следующем примере двумерный массив целых чисел инициализируется и передается в метод `Print2DArray`.  Затем метод отображает элементы этого массива.  
  
### Код  
 [!CODE [csProgGuideArrays#31](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#31)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Массивы массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md)