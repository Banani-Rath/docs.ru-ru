---
title: "Практическое руководство. Определение представления числового значения в строке (Руководство по программированию в C#) | Microsoft Docs"
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
  - "числовые строки [C#]"
  - "строки [C#], числовой"
  - "проверка входных числовых данных [C#]"
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Определение представления числового значения в строке (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Чтобы определить, является ли строка допустимым представлением указанного числового типа, воспользуйтесь статическим методом `TryParse`, реализуемым всеми простыми числовыми типами, например <xref:System.DateTime> и <xref:System.Net.IPAddress>.  В следующем примере показано, как определить, является ли число 108 допустимым типом [int](../../../csharp/language-reference/keywords/int.md).  
  
```  
int i = 0;   
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 Если строка содержит нечисловые знаки либо числовое значение слишком велико или мало для указанного типа, `TryParse` возвращает значение "false" и задает выходному параметру значение "0".  В противном случае возвращается значение "true", а выходному параметру задается числовое значение строки.  
  
> [!NOTE]
>  Строка может содержать только числовые знаки и оставаться недопустимой для типа, где используется метод `TryParse`.  Например, "256" не является допустимым значением для `byte`, однако оно допустимо для `int`. "  98.6" не является допустимым значением для `int`, однако оно допустимо для `decimal`.  
  
## Пример  
 В следующем примере показано использование `TryParse` со строковыми представлениями значений `long`, `byte` и `decimal`.  
  
 [!CODE [csProgGuideStrings#14](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStrings#14)]  
  
## Отказоустойчивость  
 Простые числовые типы также реализуют статический метод `Parse`, который вызывает исключение, если строка не является допустимым числом.  В общем оператор `TryParse` более эффективен, поскольку если число не является допустимым, он просто возвращает значение false.  
  
## Безопасность платформы .NET Framework  
 Для проверки данных, введенных пользователем в такие элементы управления, как текстовые поля и поля со списком, всегда следует использовать метод `TryParse` или `Parse`.  
  
## См. также  
 [Практическое руководство. Преобразование массива байтов в значение типа int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md)   
 [Практическое руководство. Преобразование строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)   
 [Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)   
 [Разбор числовых строк](../Topic/Parsing%20Numeric%20Strings%20in%20the%20.NET%20Framework.md)   
 [Типы форматирования](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md)