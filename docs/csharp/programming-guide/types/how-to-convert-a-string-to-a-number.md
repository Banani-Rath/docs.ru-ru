---
title: "Практическое руководство. Преобразование строки в число (руководство по программированию в C#) | Microsoft Docs"
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
  - "преобразования [C#]"
  - "преобразования [C#], строка в int"
  - "преобразование строк в int [C#]"
  - "строки [C#], преобразование в int"
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
caps.latest.revision: 34
caps.handback.revision: 34
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Преобразование строки в число (руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Вы можете преобразовывать [строку](../../../csharp/language-reference/keywords/string.md) в число с помощью методов в классе <xref:System.Convert> или с помощью метода `TryParse`, который можно найти в различных числовых типах \(int, long, float и т. д.\).  
  
 Если имеется строка, то немного более эффективно и проще вызвать метод `TryParse` \(например, `int.TryParse(“11”)`\).  Использование метода `Convert` более удобно для общих объектов, реализующих <xref:System.IConvertible>.  
  
 Вы можете использовать методы `Parse` или `TryParse` в числовом типе, который предположительно содержит строка, таком как тип <xref:System.Int32?displayProperty=fullName>.  Метод <xref:System.Convert.ToUInt32%2A?displayProperty=fullName> использует <xref:System.Int32.Parse%2A> внутри себя.  Если строка имеет недопустимый формат, `Parse` создает исключение, а `TryParse` возвращает значение [false](../../../csharp/language-reference/keywords/false.md).  
  
## Пример  
 Методы `Parse` и `TryParse` игнорируют пробелы в начале и в конце строки, но все остальные символы должны быть символами, которые образуют соответствующий числовой тип \(int, long, ulong, float, decimal и т. д.\).  Любые пробелы в символах, образующих число, приводят к ошибке.  Например, можно использовать `decimal.TryParse` для анализа «10», «10.3», «  10  », но этот метод нельзя использовать для анализа 10 из «10X», «1 0» \(обратите внимание на пробел\), «10. 3» \(обратите внимание на пробел\), «10e1» \(здесь работает `float.TryParse`\) и т. д.  
  
 В приведенных ниже примерах демонстрируются успешные и неуспешные вызовы методов `Parse` и `TryParse`.  
  
 [!CODE [csProgGuideTypes#5555](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#5555)]  
[!CODE [csProgGuideTypes#25](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#25)]  
[!CODE [csProgGuideTypes#26](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#26)]  
[!CODE [csProgGuideTypes#27](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#27)]  
[!CODE [csProgGuideTypes#28](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#28)]  
[!CODE [csProgGuideTypes#100](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#100)]  
  
## Пример  
 В следующей таблице перечислены некоторые методы класса <xref:System.Convert>, которые можно использовать.  
  
|Числовой тип|Метод|  
|------------------|-----------|  
|`decimal`|<xref:System.Convert.ToDecimal%28System.String%29>|  
|`float`|<xref:System.Convert.ToSingle%28System.String%29>|  
|`double`|<xref:System.Convert.ToDouble%28System.String%29>|  
|`short`|<xref:System.Convert.ToInt16%28System.String%29>|  
|`int`|<xref:System.Convert.ToInt32%28System.String%29>|  
|`long`|<xref:System.Convert.ToInt64%28System.String%29>|  
|`ushort`|<xref:System.Convert.ToUInt16%28System.String%29>|  
|`uint`|<xref:System.Convert.ToUInt32%28System.String%29>|  
|`ulong`|<xref:System.Convert.ToUInt64%28System.String%29>|  
  
 В данном примере вызывается метод <xref:System.Convert.ToInt32%28System.String%29?displayProperty=fullName> для преобразования входных данных типа [string](../../../csharp/language-reference/keywords/string.md) в значение типа [int](../../../csharp/language-reference/keywords/int.md).  Код перехватывает два наиболее распространенных исключения, которые могут создаваться этим методом, — <xref:System.FormatException> и <xref:System.OverflowException>.  Если число может быть увеличено без переполнения места хранения целого числа, программа добавляет к результату 1 и печатает выходные данные.  
  
 [!CODE [csProgGuideTypes#5555](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#5555)]  
[!CODE [csProgGuideTypes#24](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#24)]  
  
## См. также  
 [Типы](../../../csharp/programming-guide/types/index.md)   
 [Практическое руководство. Определение представления числового значения в строке](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)   
 [Служебная программа форматирования в .NET Framework 4](http://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)