---
title: "Использование операторов преобразования (Руководство по программированию в C#) | Microsoft Docs"
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
  - "операторы преобразования [C#]"
  - "преобразования [C#], операторы"
  - "операторы явного преобразования [C#]"
  - "операторы неявного преобразования [C#]"
  - "операторы [C#], преобразование"
  - "заданные пользователем преобразования [C#]"
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Использование операторов преобразования (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Операторы преобразования `implicit`, которые удобно использовать для использования или операторы преобразования `explicit`, которые указывают, чтения на любой код, а преобразование типа.  В этом разделе показаны оба типа оператора преобразования.  
  
> [!NOTE]
>  Дополнительные сведения о преобразовании простого типа см. в разделе [Практическое руководство. Преобразование строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [Практическое руководство. Преобразование массива байтов в значение типа int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) или <xref:System.Convert>.  
  
## Пример  
 В этом примере используется оператор явного преобразования.  Этот оператор преобразует тип значения <xref:System.Byte> в тип значения `Digit`.  Поскольку в тип Digit могут быть преобразованы не все значения типа byte, преобразование выполняется явным образом, что означает использование операции приведения, как показано в методе `Main`.  
  
 [!CODE [csProgGuideStatements#11](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#11)]  
  
## Пример  
 В этом примере демонстрируется неявное преобразование, в котором определяется оператор преобразования, выполняющий операцию, обратную описанной в предыдущем примере: преобразование значения типа `Digit` к целочисленному типу <xref:System.Byte>.  Поскольку к типу <xref:System.Byte> можно преобразовать любое значение типа Digit, нет нужды делать преобразование явным для пользователя.  
  
 [!CODE [csProgGuideStatements#12](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#12)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)   
 [is](../../../csharp/language-reference/keywords/is.md)