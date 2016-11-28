---
title: "Практическое руководство. Преобразование строки в значение типа &quot;DateTime&quot; (Руководство по программированию в C#) | Microsoft Docs"
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
  - "строки [C#], преобразование в тип DateTime"
ms.assetid: 88abef11-3a06-4b49-8dd2-61ed0e876fc3
caps.latest.revision: 21
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Преобразование строки в значение типа &quot;DateTime&quot; (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В программах часто предоставляется возможность ввода пользователями дат в виде строковых значений. Чтобы преобразовать дату в строковом формате в объект <xref:System.DateTime?displayProperty=fullName>, можно использовать метод <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=fullName> или статический метод <xref:System.DateTime.Parse%28System.String%29?displayProperty=fullName>, как показано в приведенном ниже примере.  
  
 **Язык и региональные параметры**.  В разных языках приняты разные способы записи дат.  Например, в США дата 01\/20\/2008 соответствует 20 января 2008 года.  Во французском языке такая дата приведет к созданию исключения InvalidFormatException. Связано это с тем, что во французском принята запись дат в формате День\/Месяц\/Год, а в США — Месяц\/День\/Год.  
  
 Поэтому строка 20\/01\/2008 будет разобрана во французском как 20 января 2008 года, а затем создаст исключение InvalidFormatException в английском \(США\).  
  
 Чтобы определить текущие параметры языка, можно использовать System.Globalization.CultureInfo.CurrentCulture.  
  
 Ниже приведен простой пример преобразования строки в объект dateTime.  
  
 Дополнительные примеры строк с датами см. в разделе <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=fullName>.  
  
```vb  
string dateTime = "01/08/2008 14:50:50.42"; DateTime dt = Convert.ToDateTime(dateTime); Console.WriteLine("Year: {0}, Month: {1}, Day: {2}, Hour: {3}, Minute: {4}, Second: {5}, Millisecond: {6}", dt.Year, dt.Month, dt.Day, dt.Hour, dt.Minute, dt.Second, dt.Millisecond); // Specify exactly how to interpret the string. IFormatProvider culture = new System.Globalization.CultureInfo("fr-FR", true); // Alternate choice: If the string has been input by an end user, you might // want to format it according to the current culture: // IFormatProvider culture = System.Threading.Thread.CurrentThread.CurrentCulture; DateTime dt2 = DateTime.Parse(dateTime, culture, System.Globalization.DateTimeStyles.AssumeLocal); Console.WriteLine("Year: {0}, Month: {1}, Day: {2}, Hour: {3}, Minute: {4}, Second: {5}, Millisecond: {6}", dt2.Year, dt2.Month, dt2.Day, dt2.Hour, dt2.Minute, dt2.Second, dt2.Millisecond /* Output (assuming first culture is en-US and second is fr-FR): Year: 2008, Month: 1, Day: 8, Hour: 14, Minute: 50, Second: 50, Millisecond: 420 Year: 2008, Month: 8, Day: 1, Hour: 14, Minute: 50, Second: 50, Millisecond: 420 Press any key to continue . . . */  
```  
  
## Пример  
 [!CODE [csProgGuideStrings#13](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStrings#13)]  
  
## См. также  
 [Строки](../../../csharp/programming-guide/strings/index.md)