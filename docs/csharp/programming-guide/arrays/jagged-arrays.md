---
title: "Массивы массивов (Руководство по программированию на C#) | Microsoft Docs"
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
  - "массивы [C#], неравномерный"
  - "неравномерные массивы [C#]"
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Массивы массивов (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Массив массивов — это массив, элементы которого сами являются массивами.  Элементы массива массивов могут иметь различные размеры и измерения.  Массивы массивов иногда также называются "невыровненными массивами". В следующих примерах показано, как выполняется объявление, инициализация и доступ к массивам массивов.  
  
 Ниже показано объявление одномерного массива, включающего три элемента, каждый из которых является одномерным массивом целых чисел.  
  
 [!CODE [csProgGuideArrays#19](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#19)]  
  
 Перед использованием `jaggedArray` его элементы нужно инициализировать.  Сделать это можно следующим образом.  
  
 [!CODE [csProgGuideArrays#20](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#20)]  
  
 Каждый элемент представляет собой одномерный массив целых чисел.  Первый элемент массива состоит из пяти целях чисел, второй — из четырех и третий — из двух.  
  
 Для заполнения элементов массива значениями можно также использовать инициализаторы, при этом размер массива знать не требуется.  Примеры.  
  
 [!CODE [csProgGuideArrays#21](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#21)]  
  
 Также массив можно инициализировать путем объявления.  
  
 [!CODE [csProgGuideArrays#22](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#22)]  
  
 Также можно использовать сокращенную форму.  Обратите внимание, что при инициализации элементов оператор `new` опускать нельзя, так как инициализации по умолчанию для этих элементов не существует.  
  
 [!CODE [csProgGuideArrays#23](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#23)]  
  
 Невыровненный массив является массивом массивов и поэтому его элементы являются ссылочными типами и инициализируются значением `null`.  
  
 Доступ к отдельным элементам массива выполняется следующим образом.  
  
 [!CODE [csProgGuideArrays#24](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#24)]  
  
 Массивы массивов можно смешивать с многомерными массивами.  Ниже показано объявление и инициализация одномерного массива массивов, состоящего из трех двумерных элементов различного размера.  Дополнительные сведения о двумерных массивах см. в разделе [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).  
  
 [!CODE [csProgGuideArrays#25](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#25)]  
  
 Доступ к отдельным элементам выполняется как показано в примере ниже, где отображено значение элемента `[1,0]` первого массива \(значение `5`\).  
  
 [!CODE [csProgGuideArrays#26](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#26)]  
  
 Метод `Length` возвращает число массивов, содержащихся в массиве массивов.  Например, если объявить предыдущий массив, мы получим следующее.  
  
 [!CODE [csProgGuideArrays#27](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#27)]  
  
 возвращает значение 3.  
  
## Пример  
 В этом примере выполняется создание массива, элементы которого сами являются массивами.  Каждый элемент массива имеет собственный размер.  
  
 [!CODE [csProgGuideArrays#18](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#18)]  
  
## См. также  
 <xref:System.Array>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)