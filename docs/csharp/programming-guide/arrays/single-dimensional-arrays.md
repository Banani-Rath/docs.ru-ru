---
title: "Одномерные массивы (Руководство по программированию на C#) | Microsoft Docs"
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
  - "массивы [C#], одномерный"
  - "одномерные массивы [C#]"
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Одномерные массивы (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Можно объявить массив из пяти целых чисел с одним измерением, как показано в следующем примере:  
  
 [!CODE [csProgGuideArrays#4](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#4)]  
  
 Массив содержит элементы с `array[0]` по `array[4]`.  Оператор [new](../../../csharp/language-reference/keywords/new.md) служит для создания массива и инициализации элементов массива со значениями по умолчанию.  В данном примере элементы массива инициализируются значением 0.  
  
 Массив, в котором хранятся строковые элементы, можно объявить таким же образом.  Примеры.  
  
 [!CODE [csProgGuideArrays#5](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#5)]  
  
## Инициализация массива  
 Массив можно инициализировать при объявлении. В этом случае спецификация ранга не нужна, поскольку она уже предоставлена по числу элементов в списке инициализации.  Примеры.  
  
 [!CODE [csProgGuideArrays#6](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#6)]  
  
 Строковый массив можно инициализировать таким же образом.  Ниже приведено объявление строкового массива, в котором каждый элемент инициализируется названием дня:  
  
 [!CODE [csProgGuideArrays#7](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#7)]  
  
 При инициализации массива при объявлении можно использовать следующие сочетания клавиш:  
  
 [!CODE [csProgGuideArrays#8](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#8)]  
  
 Можно объявить переменную массива без инициализации, но при присвоении массива этой переменной нужно использовать оператор `new`.  Примеры.  
  
 [!CODE [csProgGuideArrays#9](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#9)]  
  
 В C\# 3.0 поддерживаются неявно типизированные массивы.  Дополнительные сведения см. в разделе [Неявно типизированные массивы](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## Массивы типов значений и ссылочных типов.  
 Рассмотрим следующие объявления массива:  
  
 [!CODE [csProgGuideArrays#10](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#10)]  
  
 Результат этого оператора зависит от того, является ли `SomeType` типом значения или ссылочным типом.  Если это тип значения, оператор создает массив из 10 элементов типа `SomeType`.  Если `SomeType` — ссылочный тип, оператор создает массив из 10 элементов, Каждый из которых инициализируется нулевой ссылкой.  
  
 Дополнительные сведения о типах значения и ссылочных типах см. в разделе [Типы](../../../csharp/language-reference/keywords/types.md).  
  
## См. также  
 <xref:System.Array>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Массивы массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md)